---
title: sp_msx_enlist (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_msx_enlist_TSQL
- sp_msx_enlist
dev_langs:
- TSQL
helpviewer_keywords:
- sp_msx_enlist
ms.assetid: ceb3b2bc-0cc4-48d8-9bdc-6a809556e35f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 551d0796ce534f77d4994064a9af032f34f81f04
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85893473"
---
# <a name="sp_msx_enlist-transact-sql"></a>sp_msx_enlist (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Добавляет текущий сервер к списку доступных серверов на главном сервере.  
  
> [!CAUTION]  
>  Хранимая процедура **sp_msx_enlist** редактирует реестр. Редактировать реестр вручную не рекомендуется, так как неуместные или неверные изменения могут серьезно нарушить конфигурацию системы. Пользоваться программой редактирования реестра должны только опытные пользователи. Дополнительные сведения см. в документации Microsoft Windows.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_msx_enlist [@msx_server_name =] 'msx_server'   
     [, [@location =] 'location']  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @msx_server_name = ] 'msx_server'`Имя сервера администрирования многосерверной версии (Master). Аргумент *msx_server* имеет тип **sysname**и не имеет значения по умолчанию.  
  
`[ @location = ] 'location'`Расположение добавляемого целевого сервера. *Location* имеет тип **nvarchar (100)** и значение по умолчанию NULL.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="result-sets"></a>Результирующие наборы  
 None  
  
## <a name="permissions"></a>Разрешения  
 По умолчанию разрешения на выполнение этой процедуры имеют члены предопределенной роли сервера **sysadmin** .  
  
## <a name="examples"></a>Примеры  
 В следующем примере текущий сервер прикрепляется к главному серверу `AdventureWorks1`. Местоположение текущего сервера — `Building 21, Room 309, Rack 5`.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
    N'Building 21, Room 309, Rack 5' ;  
GO  
```  
  
## <a name="see-also"></a>См. также  
 [sp_msx_defect &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-msx-defect-transact-sql.md)   
 [Системные хранимые процедуры &#40;&#41;Transact-SQL](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [xp_cmdshell &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/xp-cmdshell-transact-sql.md)  
  
  
