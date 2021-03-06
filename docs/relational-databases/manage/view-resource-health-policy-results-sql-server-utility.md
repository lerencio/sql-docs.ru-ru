---
title: Просмотр результатов действия политики исправности ресурсов (служебная программа SQL Server) | Документация Майкрософт
description: Узнайте, как использовать SQL Server Management Studio для просмотра результатов политики работоспособности ресурсов служебной программы SQL Server для экземпляров SQL Server и приложений уровня данных.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 80cb14fb-f4c6-4be2-ba17-eb4e4cddd35f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 83cbdce1203cbe28f58c676da361091880a9f675
ms.sourcegitcommit: 01297f2487fe017760adcc6db5d1df2c1234abb4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86197252"
---
# <a name="view-resource-health-policy-results-sql-server-utility"></a>Просмотр результатов политики исправности ресурсов (служебная программа SQL Server)

[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

Панель мониторинга служебной программы в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] позволяет просмотреть параметры служебной программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для управляемых экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и приложений уровня данных. Дополнительные сведения см. в разделе [Функции и задачи служебной программы SQL Server](../../relational-databases/manage/sql-server-utility-features-and-tasks.md).  

##  <a name="SSMSProcedure"></a>

### <a name="view-sql-server-utility-resource-health-policy-results"></a>Просмотр результатов политики исправности ресурсов (SQL Server Utility)  

1. В [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (SSMS) выберите **Вид**, затем выберите **Обозреватель программ**, чтобы открыть панель навигации обозревателя программ. Чтобы открыть панель содержимого, выберите **Вид**, а затем выберите **Содержимое обозревателя программ**.  

2. На панели навигации выберите ![подключиться к программе](../../relational-databases/manage/media/connect-to-utility.gif "Connect_to_Utility")**Подключиться к программе**. Если точка управления служебной программой еще не создана либо экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или приложения уровня данных не зарегистрированы в служебной программе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , см. раздел [Функции и задачи служебной программы SQL Server](../../relational-databases/manage/sql-server-utility-features-and-tasks.md).  

3. Выберите узел точки управления служебной программой (UCP), чтобы отобразить сводные данные по управляемым экземплярам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и приложениям уровня данных (чтобы обновить данные, нажмите правую кнопку мыши). Данные панели мониторинга отображаются в области содержимого.  

4. Выберите узел **Управляемые экземпляры**, чтобы открыть список данных по управляемым экземплярам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (чтобы обновить данные, нажмите правую кнопку мыши). Данные в представлении списка отображаются на панели содержимого.  

5. Выберите узел **Развернутые приложения уровня данных**, чтобы отобразить список данных по приложениям уровня данных (чтобы обновить данные, нажмите правую кнопку мыши). Данные в представлении списка отображаются на панели содержимого.  

## <a name="see-also"></a>См. также:

- [Функции и задачи служебной программы SQL Server](../../relational-databases/manage/sql-server-utility-features-and-tasks.md)
- [Уменьшение уровня шума в политиках загрузки ЦП (служебная программа SQL Server)](../../relational-databases/manage/reduce-noise-in-cpu-utilization-policies-sql-server-utility.md)
- [Подробные сведения о развернутом приложении уровня данных (служебная программа SQL Server)](https://msdn.microsoft.com/library/79c41dd9-abcb-434e-9326-00a341d5c867)
- [Подробные сведения об управляемом экземпляре (служебная программа SQL Server)](https://msdn.microsoft.com/library/6e51b7bb-a733-4852-8c33-7f4dbdf931c2)
- [Администрирование программ (служебная программа SQL Server)](https://msdn.microsoft.com/library/3e5a00c3-8905-40f0-9ddc-d924df9c2f0d)