---
title: Проверка подсистемы ввода-вывода диска на наличие проблем повторного чтения — управление на основе политик
description: Это правило проверяет журнал событий на наличие сообщения об ошибке 825 на SQL Server, которое указывает, что SQL Server не удалось считать данные с диска при первой попытке.
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: cedf4097-5b73-4964-9935-74a101847019
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: dd26814ac9b1a1ab2c1f7c8b00705d264a96a735
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85655044"
---
# <a name="check-disk-input-output-subsystem-for-read-retry-problems"></a>Проверка на наличие проблем повторного чтения в подсистеме дискового ввода-вывода
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  Это правило проверяет журнал событий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на наличие сообщения об ошибке 825. Это сообщение показывает, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удалось считать данные с диска с первой попытки. Оно указывает на серьезную проблему в подсистеме дискового ввода-вывода. Это сообщение не указывает на текущую проблему [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Однако проблема подсистемы дискового ввода-вывода может привести к потере данных или повреждению базы данных, если она не будет решена.  
  
## <a name="best-practices-recommendations"></a>Рекомендации  
 Следующие действия помогут обнаружить и исправить базовую проблему оборудования.  
  
-   Просмотрите журнал ошибок и переменный текст данного сообщения, объясняющие суть проблемы.  
  
-   Проверьте дисковую систему. Проблема может быть связана с жесткими дисками, контроллерами дисков, контроллерами дисковых массивов или драйверами дисков.  
  
-   Обратитесь к производителю диска за новейшими утилитами проверки состояния дисковой системы.  
  
-   Обратитесь к производителю диска за новейшими обновлениями драйверов.  
  
## <a name="for-more-information"></a>Дополнительные сведения см. в разделе  
 [MSSQLSERVER_825](../errors-events/mssqlserver-825-database-engine-error.md)  
  
 [Основные операции ввода-вывода в SQL Server, раздел 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))  
  
  
