---
title: sp_script_synctran_commands (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_script_synctran_commands
- sp_script_synctran_commands_TSQL
helpviewer_keywords:
- sp_script_synctran_commands
ms.assetid: f132694a-dd05-405b-9d84-21acce9e564a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 697cba4e04483e28fe0099096916391057c1568a
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85899213"
---
# <a name="sp_script_synctran_commands-transact-sql"></a>Хранимая процедура sp_script_synctran_commands (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Формирует скрипт, содержащий вызовы **sp_addsynctrigger** , применяемые на подписчиках для обновляемых подписок. Существует один **sp_addsynctrigger** вызов для каждой статьи в публикации. Созданный скрипт также содержит **sp_addqueued_artinfoные** вызовы, создающие **MSsubsciption_articles** таблицу, необходимую для обработки публикаций в очереди. Эта хранимая процедура выполняется на издателе в базе данных публикации.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_script_synctran_commands [@publication = ] 'publication'  
    [ , [@article = ] 'article']  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @publication = ] 'publication'`Имя публикации, для которой создается скрипт. Аргумент *publication* имеет тип **sysname**и не имеет значения по умолчанию.  
  
`[ @article = ] 'article'`Имя статьи, для которой создается скрипт. Аргумент *article* имеет тип **sysname**и значение по умолчанию **ALL**, которое указывает, что все статьи включены в скрипт.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 **0** (успешное завершение) или **1** (сбой)  
  
## <a name="results-set"></a>Результирующий набор  
 **sp_script_synctran_commands** возвращает результирующий набор, состоящий из одного столбца **nvarchar (4000)** . Результирующий набор формирует полные скрипты, необходимые для создания вызовов **sp_addsynctrigger** и **sp_addqueued_artinfo** , применяемых на подписчиках.  
  
## <a name="remarks"></a>Комментарии  
 **sp_script_synctran_commands** используется в моментальных снимках и репликации транзакций.  
  
 **sp_addqueued_artinfo** используется для обновляемых посредством очередей подписок.  
  
## <a name="permissions"></a>Разрешения  
 Только члены предопределенной роли сервера **sysadmin** или предопределенной роли базы данных **db_owner** могут выполнять **sp_script_synctran_commands**.  
  
## <a name="see-also"></a>См. также  
 [sp_addsynctriggers &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addsynctriggers-transact-sql.md)   
 [sp_addqueued_artinfo &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addqueued-artinfo-transact-sql.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
