---
title: sp_helpreplicationoption (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_helpreplicationoption
- sp_helpreplicationoption_TSQL
helpviewer_keywords:
- sp_helpreplicationoption
ms.assetid: ef988dbc-dd0b-4132-80ab-81eebec1cffe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e04daaa5be757df60f07a8bd9205e1fd44f95502
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85775746"
---
# <a name="sp_helpreplicationoption-transact-sql"></a>Хранимая процедура sp_helpreplicationoption (Transact-SQL)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

  Показывает типы параметров репликации, включенных на сервере. Эта хранимая процедура выполняется на любом сервере в любой базе данных.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_helpreplicationoption [ [ @optname =] 'option_name' ]  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @optname = ] 'option_name'`Имя параметра репликации, для которого необходимо выполнить запрос. Аргумент *option_name* имеет тип **sysname**и значение по умолчанию NULL.  
  
|Применение|Описание:|  
|-----------|-----------------|  
|**транзакций**|Результирующий набор возвращается, если включена репликация транзакций.|  
|**AutoMerge**|Результирующий набор возвращается, если включена репликация слиянием.|  
|NULL (по умолчанию)|Результирующий набор не возвращается.|  
  
## <a name="result-sets"></a>Результирующие наборы  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**optname**|**sysname**|Имя параметра репликации, может быть одним из следующих:<br /><br /> **транзакций**<br /><br /> **AutoMerge**|  
|**value**|**bit**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**major_version**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**minor_version**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**редакции**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**install_failures**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="remarks"></a>Примечания  
 **sp_helpreplicationoption** используется для получения сведений о параметрах репликации, включенных на определенном сервере. Чтобы получить сведения о конкретной базе данных, используйте **sp_helpreplicationdboption**.  
  
## <a name="permissions"></a>Разрешения  
 Разрешения на выполнение по умолчанию имеют роль **Public** .  
  
## <a name="see-also"></a>См. также  
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
