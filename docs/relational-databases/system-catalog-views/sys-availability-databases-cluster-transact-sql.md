---
title: sys. availability_databases_cluster (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.availability_databases_cluster_TSQL
- sys.availability_databases_cluster
- availability_databases_cluster_TSQL
- availability_databases_cluster
dev_langs:
- TSQL
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
- Availability Groups [SQL Server], WSFC clusters
- sys.availability_databases_cluster catalog view
- Availability Groups [SQL Server], databases
ms.assetid: 8d9c57e5-7f39-4315-b466-92748231140a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: c520cf9e836f8db051599ed00735763c85632aab
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85649124"
---
# <a name="sysavailability_databases_cluster-transact-sql"></a>sys.availability_databases_cluster (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Содержит по одной строке для каждой базы данных доступности на экземпляре, на котором [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] размещена реплика доступности для любой Always on группы доступности в отказоустойчивом кластере Windows Server (WSFC), независимо от того, присоединена ли локальная база данных копии к группе доступности.  
  
> [!NOTE]  
>  При добавлении базы данных в группу доступности база данных-источник автоматически присоединяется к группе. Базы данных-получатели необходимо подготовить на каждой из вторичных реплик до того, как их можно будет присоединить к группе доступности.   
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**group_id**|**uniqueidentifier**|Уникальный идентификатор группы доступности, в которой участвует база данных, если такая группа имеется.<br /><br /> NULL = база данных не является частью реплики доступности в группе доступности.|  
|**group_database_id**|**uniqueidentifier**|Уникальный идентификатор базы данных в группе доступности, в которой участвует база данных, если такая группа имеется. **group_database_id** одинаковы для этой базы данных в первичной реплике и на каждой вторичной реплике, в которой база данных была присоединена к группе доступности.<br /><br /> NULL = база данных не является частью реплики доступности в любой группе доступности.|  
|**database_name**|**sysname**|Имя базы данных, которая добавлена к группе доступности.|  
  
## <a name="permissions"></a>Разрешения  
 Если вызывающий объект **sys. availability_databases_cluster** не является владельцем базы данных, то минимальным разрешениями, необходимыми для просмотра соответствующей строки, являются разрешения на уровне сервера ALTER ANY DATABASE или View любое базу данных или разрешение CREATE DATABASE в базе данных **master** .  
  
## <a name="see-also"></a>См. также  
 [sys.availability_groups (Transact-SQL)](../../relational-databases/system-catalog-views/sys-availability-groups-transact-sql.md)   
 [sys.databases (Transact-SQL)](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md)   
 [sys. dm_hadr_database_replica_states &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-states-transact-sql.md)   
 [sys. dm_hadr_database_replica_cluster_states &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql.md)   
 [Общие сведения о группах доступности Always On &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)  
  
  
