---
title: sys. dm_pdw_nodes_database_encryption_keys (Transact-SQL)
ms.custom: seo-dt-2019
ms.date: 03/07/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: e7fd02b2-5d7e-4816-a0af-b58ae2ac3f7a
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: 2d30ceadf292387900469fe99018ed7e2fdb361d
ms.sourcegitcommit: 01297f2487fe017760adcc6db5d1df2c1234abb4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86196642"
---
# <a name="sysdm_pdw_nodes_database_encryption_keys-transact-sql"></a>sys. dm_pdw_nodes_database_encryption_keys (Transact-SQL)
[!INCLUDE[applies-to-version/asa-pdw](../../includes/applies-to-version/asa-pdw.md)]

  Возвращает сведения о состоянии шифрования базы данных и о связанных ключах шифрования базы данных. **sys. dm_pdw_nodes_database_encryption_keys** предоставляет эти сведения для каждого узла. Дополнительные сведения о шифровании базы данных см. в разделе [прозрачное шифрование данных (SQL Server PDW)](../../analytics-platform-system/transparent-data-encryption.md).  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|database_id|**int**|Идентификатор физической базы данных на каждом узле.|  
|encryption_state|**int**|Указывает, является ли база данных на этом узле зашифрованной или не зашифрованной.<br /><br /> 0 = нет ключа шифрования базы данных, нет шифрования<br /><br /> 1 = не зашифрована<br /><br /> 2 = выполняется шифрование<br /><br /> 3 = зашифрована<br /><br /> 4 = выполняется изменение ключа<br /><br /> 5 = выполняется расшифровка<br /><br /> 6 = выполняется изменение защиты (сертификат, который шифрует ключ шифрования базы данных, изменяется.)|  
|create_date|**datetime**|Отображает дату создания ключа шифрования.|  
|regenerate_date|**datetime**|Отображает дату повторного создания ключа шифрования.|  
|modify_date|**datetime**|Отображает дату изменения ключа шифрования.|  
|set_date|**datetime**|Отображает дату применения ключа шифрования к базе данных.|  
|opened_date|**datetime**|Показывает, когда ключ базы данных был открыт в последний раз.|  
|key_algorithm|**varchar (?)**|Отображает алгоритм, используемый для ключа.|  
|key_length|**int**|Отображает длину ключа.|  
|encryptor_thumbprint|**варбин**|Показывает отпечаток шифратора.|  
|percent_complete|**real**|Процент выполнения шифрования базы данных. Значение 0, если изменения состояния не было.|  
|node_id|**int**|Уникальный числовой идентификатор, связанный с узлом.|  
  
## <a name="permissions"></a>Разрешения  
 Необходимо разрешение VIEW SERVER STATE на сервере.  
  
## <a name="examples-sssdwfull-and-sspdw"></a>Примеры: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] и [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 В следующем примере объединяются `sys.dm_pdw_nodes_database_encryption_keys` с другими системными таблицами для указания состояния шифрования для каждого узла защищенных баз данных TDE.  
  
```  
SELECT D.database_id AS DBIDinMaster, D.name AS UserDatabaseName,   
PD.pdw_node_id AS NodeID, DM.physical_name AS PhysDBName,   
keys.encryption_state  
FROM sys.dm_pdw_nodes_database_encryption_keys AS keys  
JOIN sys.pdw_nodes_pdw_physical_databases AS PD  
    ON keys.database_id = PD.database_id AND keys.pdw_node_id = PD.pdw_node_id  
JOIN sys.pdw_database_mappings AS DM  
    ON DM.physical_name = PD.physical_name  
JOIN sys.databases AS D  
    ON D.database_id = DM.database_id  
ORDER BY D.database_id, PD.pdw_node_ID;  
```  
  
## <a name="see-also"></a>См. также  
 [Динамические административные представления хранилища данных SQL и параллельного хранилища данных &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)   
 [Создание ключа шифрования базы данных &#40;&#41;Transact-SQL](../../t-sql/statements/create-database-encryption-key-transact-sql.md)   
 [&#40;&#41;Transact-SQL в инструкции ALTER DATABASE ENCRYPTION KEY](../../t-sql/statements/alter-database-encryption-key-transact-sql.md)   
 [DROP DATABASE ENCRYPTION KEY (Transact-SQL)](../../t-sql/statements/drop-database-encryption-key-transact-sql.md)  
  
  

