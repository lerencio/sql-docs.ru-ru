---
title: Что такое контроллер
titleSuffix: SQL Server big data clusters
description: В этой статье описывается контроллер в кластере больших данных SQL Server.
author: mihaelablendea
ms.author: mihaelab
ms.reviewer: mikeray
ms.date: 11/04/2019
ms.topic: conceptual
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: 5a294bf705e4caf4a79c0f67ce925187e24c0f00
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85730702"
---
# <a name="what-is-the-controller-on-a-sql-server-big-data-cluster"></a>Что такое контроллер в кластере больших данных SQL Server

[!INCLUDE[SQL Server 2019](../includes/applies-to-version/sqlserver2019.md)]

Контроллер содержит основную логику для развертывания кластера больших данных и управления им. Он отвечает за все взаимодействие с Kubernetes, экземплярами SQL Server, входящими в кластер, и другими компонентами, такими как HDFS и Spark.

Служба контроллера предоставляет следующие основные возможности:

- управление жизненным циклом кластера: конфигурации начальной загрузки, удаления и обновления кластера;
- управление главными экземплярами SQL Server;
- управление пулами вычислительных ресурсов, данных и носителей;
- предоставление средств мониторинга для наблюдения за состоянием кластера;
- предоставление средств устранения неполадок для выявления и устранения непредвиденных проблем;
- управление безопасностью кластера:
  - защита конечных точек кластера;
  - управление пользователями и ролями;
  - настройка учетных данных для обмена данными внутри кластера.

## <a name="deploying-the-controller-service"></a>Развертывание службы контроллера

Контроллер разворачивается и размещается в том же пространстве имен Kubernetes, в котором клиент создает кластер больших данных. Эта служба устанавливается администратором Kubernetes во время начальной загрузки кластера с помощью программы командной строки **azdata**. Дополнительные сведения см. в статье [Начало работы с [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)]](deploy-get-started.md).

В результате рабочего процесса создания на основе Kubernetes развертывается полнофункциональный кластер больших данных SQL Server, который включает в себя все компоненты, описанные в [обзорной статье](big-data-cluster-overview.md). Рабочий процесс начальной загрузки сначала создает службу контроллера, которая после развертывания будет координировать установку и настройку остальных служб, входящих в состав главного пула, пулов вычислительных ресурсов, данных и носителей.

## <a name="managing-the-cluster-through-the-controller-service"></a>Управление кластером с помощью службы контроллера

Вы можете управлять кластером посредством службы контроллера с помощью команд **azdata**. Если в том же пространстве имен развертываются дополнительные объекты Kubernetes, например pod, служба контроллера не управляет ими и не отслеживает их. Для управления кластером на уровне Kubernetes можно также использовать команды **kubectl**. Дополнительные сведения см. в разделе [Мониторинг и устранение неполадок [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)]](cluster-troubleshooting-commands.md).

Контроллер и объекты Kubernetes (наборы с отслеживанием состояния, объекты pod, секреты и т. д.), создаваемые для кластера больших данных, размещаются в выделенном пространстве имен Kubernetes. Администратор кластера Kubernetes предоставляет службе контроллера разрешение на управление всеми ресурсами в этом пространстве имен.  Политика RBAC для этого сценария настраивается автоматически в процессе начального развертывания кластера с помощью **azdata**.

### <a name="azdata"></a>azdata

**azdata** — это служебная программа командной строки на языке Python, которая позволяет администраторам кластера провести начальную загрузку и управлять кластером больших данных с помощью интерфейсов REST API, предоставляемых службой контроллера.

## <a name="controller-service-security"></a>Безопасность службы контроллера

Весь обмена данными со службой контроллера осуществляется через REST API по протоколу HTTPS. Самозаверяющий сертификат создается автоматически во время начальной загрузки. 

Проверка подлинности в конечной точке службы контроллера использует удостоверение Active Directory или производится на основе имени пользователя и пароля. Эти учетные данные подготавливаются во время начальной загрузки кластера с использованием входных данных для переменных среды `AZDATA_USERNAME` и `AZDATA_PASSWORD`.

> [!NOTE]
> Пароль должен соответствовать [требованиям к сложности пароля для SQL Server](https://docs.microsoft.com/sql/relational-databases/security/password-policy?view=sql-server-2017).

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения о [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)] см. в следующих ресурсах.

- [Что такое [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ver15.md)]?](big-data-cluster-overview.md)
- [Семинар. Архитектура [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)] Майкрософт](https://github.com/microsoft/sqlworkshops-bdc)
