---
title: sys. dm_pdw_component_health_alerts (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: conceptual
ms.assetid: 88f05392-1e97-4693-ba60-a4910af3c000
author: CarlRabeler
ms.author: carlrab
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: d0a3d2a3b85f0b6445229812316cf7893badd344
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87396648"
---
# <a name="sysdm_pdw_component_health_alerts-transact-sql"></a>sys. dm_pdw_component_health_alerts (Transact-SQL)
[!INCLUDE [pdw](../../includes/applies-to-version/pdw.md)]

  Хранит ранее выданные предупреждения о компонентах устройства.  
  
|Имя столбца|Тип данных|Description|Диапазон|  
|-----------------|---------------|-----------------|-----------|  
|pdw_node_id|**int**|Уникальный идентификатор [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] узла.<br /><br /> pdw_node_id, component_id, component_instance_id, alert_id и alert_instance_id образуют ключ для этого представления.|NOT NULL|  
|component_id|**int**|Идентификатор компонента. См. раздел [sys. pdw_health_components &#40;&#41;Transact-SQL ](../../relational-databases/system-catalog-views/sys-pdw-health-components-transact-sql.md).<br /><br /> pdw_node_id, component_id, component_instance_id, alert_id и alert_instance_id образуют ключ для этого представления.|NOT NULL|  
|component_instance_id|**nvarchar(255)**|pdw_node_id, component_id, component_instance_id, alert_id и alert_instance_id образуют ключ для этого представления.|NOT NULL|  
|alert_id|**int**|Идентификатор для типа оповещения. См. раздел [sys. pdw_health_alerts &#40;&#41;Transact-SQL ](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md).<br /><br /> pdw_node_id, component_id, component_instance_id, alert_id и alert_instance_id образуют ключ для этого представления.|NOT NULL|  
|alert_instance_id|**nvarchar (36)**|Определяет экземпляр данного предупреждения.<br /><br /> pdw_node_id, component_id, component_instance_id, alert_id и alert_instance_id образуют ключ для этого представления.|NOT NULL|  
|previous_value|**nvarchar(255)**|Используется, если оповещение имеет тип StatusChange. Это состояние предыдущего компонента. Значение равно NULL для предупреждений типа threshold. Список типов оповещений см. в разделе [sys. pdw_health_alerts &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md) .|NULL|  
|current_value|**nvarchar(255)**|Используется, если оповещение имеет тип StatusChange. Это текущее состояние компонента. Значение равно NULL для предупреждений типа threshold. Список типов оповещений см. в разделе [sys. pdw_health_alerts &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/sys-pdw-health-alerts-transact-sql.md) .|NULL|  
|create_time|**datetime**|Время и Дата создания предупреждения.|NOT NULL|  
  
## <a name="see-also"></a>См. также  
 [Динамические административные представления хранилища данных SQL и параллельного хранилища данных &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
