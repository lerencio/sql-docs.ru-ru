---
title: sp_db_increased_partitions | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_db_increased_partitions_TSQL
- sp_db_increased_partitions
dev_langs:
- TSQL
helpviewer_keywords:
- sp_db_increased_partitions
ms.assetid: a8c043ec-b504-4929-ac0e-8babaa99d989
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e73f98e2548427ae8d102b56e729c2bd21235572
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85867748"
---
# <a name="sp_db_increased_partitions"></a>sp_db_increased_partitions
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Включает или отключает поддержку до 15 000 секций для указанной базы данных.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_dp_increased_partitions   
[ @dbname ] = 'database_name'   
[ , [ @increased_partitions = ] 'increased_partitions' ] [;]  
```  
  
## <a name="arguments"></a>Аргументы  
 [ @dbname =] "*database_name*"  
 Имя базы данных. Аргумент *dbname* имеет тип **sysname** и значение по умолчанию NULL. Если параметр *dbname* не указан, используется текущая база данных.  
  
 [ @increased_partitions =] "*increased_partitions*"  
 Включает или выключает поддержку 15 000 секций для указанной базы данных. *increased_partitions* имеет тип **varchar (6)** и значение по умолчанию NULL. Для включения поддержки используются значения ON или TRUE, а для выключения — OFF или FALSE. Если *increased_partitions* не указан, процедура возвращает 1, чтобы указать, что поддержка включена для указанной базы данных, или значение 0, чтобы указать, что поддержка отключена.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 0 (успешное завершение) или 1 (неуспешное завершение)  
  
## <a name="permissions"></a>Разрешения  
 Необходимо разрешение ALTER DATABASE для указанной базы данных.  
  
  
