---
title: '@@MAX_CONNECTIONS (Transact-SQL) | Документы Майкрософт'
ms.custom: ''
ms.date: 09/18/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- '@@MAX_CONNECTIONS'
- '@@MAX_CONNECTIONS_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- simultaneous connections [SQL Server]
- maximum number of simultaneous user connections
- '@@MAX_CONNECTIONS function'
- connections [SQL Server], simultaneous
- number of simultaneous user connections
ms.assetid: 57eb9f4b-548f-4212-9684-a11d831c4732
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 5aef95dbc330d59992513823abcb572ff3c98d8f
ms.sourcegitcommit: 768f046107642f72693514f51bf2cbd00f58f58a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87110381"
---
# <a name="x40x40max_connections-transact-sql"></a>&#x40;&#x40;MAX_CONNECTIONS (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Возвращает максимально допустимое количество одновременных соединений пользователя с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Возвращаемое значение необязательно является заданным на настоящий момент значением.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
@@MAX_CONNECTIONS  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>Типы возвращаемых данных
 **integer**  
  
## <a name="remarks"></a>Remarks  
 Фактическое допустимое количество пользовательских соединений также зависит от установленной версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и от ограничений, налагаемых приложениями и оборудованием.  
  
 Чтобы настроить меньшее количество соединений в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], используйте процедуру **sp_configure**.  
  
## <a name="examples"></a>Примеры  
 В ходе выполнения следующего примера возвращается максимально допустимое количество одновременных соединений пользователей с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Предполагается, что экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не настраивался для уменьшения количества соединений.  
  
```  
SELECT @@MAX_CONNECTIONS AS 'Max Connections';  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
Max Connections  
---------------  
32767            
```  
  
## <a name="see-also"></a>См. также:  
 [sp_configure](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)   
 [Функции настройки](../../t-sql/functions/configuration-functions-transact-sql.md)   
 [Настройка параметра конфигурации сервера user connections](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md)  
  
  
