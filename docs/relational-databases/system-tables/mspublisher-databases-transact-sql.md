---
title: MSpublisher_databases (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSpublisher_databases
- MSpublisher_databases_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSpublisher_databases system table
ms.assetid: 59b0166e-a64c-46b8-befc-c222fa1ccce2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: cc73f32e217d7f8b3a5d0b3a23113a8f99531d2b
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889570"
---
# <a name="mspublisher_databases-transact-sql"></a>MSpublisher_databases (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Таблица **MSpublisher_databases** содержит по одной строке для каждой пары базы данных издателя или издателя, обслуживаемой локальным распространителем. Эта таблица хранится в базе данных распространителя.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**publisher_id**|**smallint**|Идентификатор издателя.|  
|**publisher_db**|**sysname**|Имя базы данных издателя.|  
|**идентификатор**|**int**|Идентификатор строки.|  
|**publisher_engine_edition**|**int**|Выпуск издателя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], который может иметь следующие значения.<br /><br /> **10** = персональный выпуск<br /><br /> **11** = Desktop Engine (MSDE)<br /><br /> **20** = Стандартный<br /><br /> **21** = Рабочая группа<br /><br /> **30** = Enterprise (ознакомительная версия)<br /><br /> **31** = разработчик<br /><br /> **40** = Express (экспресс-выпуск не может быть издателем. Это значение вставлено для обеспечения полноты.)|  
  
## <a name="see-also"></a>См. также  
 [Таблицы репликации (Transact-SQL)](../../relational-databases/system-tables/replication-tables-transact-sql.md)  
  
  
