---
title: '@@SERVERNAME (Transact-SQL) | Документы Майкрософт'
ms.custom: ''
ms.date: 09/07/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- '@@SERVERNAME'
- '@@SERVERNAME_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- '@@SERVERNAME function'
- local servers [SQL Server]
ms.assetid: b0ef33fb-954a-4294-b05b-a87c14ce25a3
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: bf55af418ce48a62d122362996dc9a7151cfa30f
ms.sourcegitcommit: 768f046107642f72693514f51bf2cbd00f58f58a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87110789"
---
# <a name="x40x40servername-transact-sql"></a>@@SERVERNAME (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Возвращает имя локального сервера, на котором работает [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
 ![Значок ссылки на статью](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
@@SERVERNAME  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>Типы возвращаемых данных
 **nvarchar**  
  
## <a name="remarks"></a>Remarks  
 Программа установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] присваивает серверу имя компьютера. Чтобы изменить имя сервера, выполните процедуру **sp_addserver**, а затем перезапустите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 При наличии нескольких установленных экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] функция @@SERVERNAME возвращает указанные ниже сведения об имени локального сервера, если это имя не было изменено после установки.  
  
|Экземпляр|Информация о сервере|  
|--------------|------------------------|  
|Экземпляр по умолчанию|'*имя_сервера*'|  
|Именованный экземпляр|'*имя_сервера*\\*имя_экземпляра*'|  
|Экземпляр отказоустойчивого кластера — экземпляр по умолчанию|"*сетевое_имя_экземпляра_отказоустойчивого_кластера_windows_server*"|  
|Экземпляр отказоустойчивого кластера — именованный экземпляр|"*сетевое_имя_экземпляра_отказоустойчивого_кластера_windows_server*\\*имя_экземпляра*"|  
  
 Хотя функция @@SERVERNAME и свойство SERVERNAME функции SERVERPROPERTY могут возвращать строки в похожих форматах, эта информация может различаться. Свойство SERVERNAME автоматически сообщает об изменениях сетевого имени компьютера.  
  
 Функция @@SERVERNAME, напротив, не сообщает о таких изменениях. Функция @@SERVERNAME информирует об изменении имени локального сервера, которое было выполнено с помощью хранимых процедур **sp_addserver** или **sp_dropserver**.  
  
## <a name="examples"></a>Примеры  
 Следующий пример демонстрирует использование процедуры `@@SERVERNAME`.  
  
```  
SELECT @@SERVERNAME AS 'Server Name'  
```  
  
 Ниже приводится образец результирующего набора.  
  
```  
Server Name  
---------------------------------  
ACCTG  
  
```  
  
## <a name="see-also"></a>См. также:  
 [Функции настройки (Transact-SQL)](../../t-sql/functions/configuration-functions-transact-sql.md)   
 [SERVERPROPERTY (Transact-SQL)](../../t-sql/functions/serverproperty-transact-sql.md)   
 [sp_addserver (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-addserver-transact-sql.md)  
  
  
