---
title: SET RESULT_SET_CACHING (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 04/16/2020
ms.prod: sql
ms.prod_service: sql-data-warehouse
ms.reviewer: jrasnick
ms.technology: t-sql
ms.topic: language-reference
f1_keywords: ''
dev_langs:
- TSQL
helpviewer_keywords: ''
author: XiaoyuMSFT
ms.author: xiaoyul
monikerRange: =azure-sqldw-latest || = sqlallproducts-allversions
ms.openlocfilehash: c975242a65da5ef29374267262deb6d8bf370f25
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87397023"
---
# <a name="set-result-set-caching-transact-sql"></a>SET RESULT SET CACHING (Transact-SQL) 

[!INCLUDE [asa](../../includes/applies-to-version/asa.md)]

Определяет поведение кэширования результирующего набора для текущего сеанса клиента.  

Применимо к: хранилищу данных SQL Azure  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис

```syntaxsql
SET RESULT_SET_CACHING { ON | OFF };
```  
  
## <a name="remarks"></a>Remarks  

Выполните эту команду при подключении к пользовательской базе данных, для которой требуется настроить параметр result_set_caching.

**ON**   
Включает кэширование результирующего набора для текущего сеанса клиента.  Для кэширования результирующих наборов невозможно указать значение ON для сеанса, если на уровне базы данных указано значение OFF.

**OFF**   
Отключает кэширование результирующего набора для текущего сеанса клиента.

## <a name="examples"></a>Примеры

В [sys.dm_pdw_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql) запросите столбец result_cache_hit, используя request_id запроса, чтобы определить, был ли запрос результатов выполнен с попаданием в кэше или промахом кэша.

```sql
SELECT result_cache_hit
FROM sys.dm_pdw_exec_requests
WHERE request_id = 'QID58286'
```

## <a name="permissions"></a>Разрешения

Требуется членство в роли public.

## <a name="see-also"></a>См. также раздел

- [Performance tuning with result set caching](/azure/sql-data-warehouse/performance-tuning-result-set-caching) (Настройка производительности путем кэширования результирующего набора)
- [Параметры ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options?view=azure-sqldw-latest)
- [ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql?view=azure-sqldw-latest)
- [DBCC SHOWRESULTCACHESPACEUSED (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-showresultcachespaceused-transact-sql)
- [DBCC DROPRESULTSETCACHE (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-dropresultsetcache-transact-sql)
