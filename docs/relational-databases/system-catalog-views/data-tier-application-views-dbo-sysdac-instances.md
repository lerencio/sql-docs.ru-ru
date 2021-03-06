---
title: dbo.sysdac_instances (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dbo.sysdac_instances_TSQL
- sysdac_instances
- sysdac_instances_TSQL
- dbo.sysdac_instances
dev_langs:
- TSQL
helpviewer_keywords:
- dbo.sysdac_instances
- sysdac_instances
ms.assetid: 28285f3d-3889-439f-8b24-3bdef08e46b4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 18031fac584eea39e5901276b597fc556263b18e
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85752975"
---
# <a name="data-tier-application-views---dbosysdac_instances"></a>Представления приложений уровня данных — dbo.sysdac_instances
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Отображает по одной строке для каждого экземпляра приложения уровня данных (DAC), развернутого на экземпляре [!INCLUDE[ssDE](../../includes/ssde-md.md)]. sysdac_instances принадлежит схеме dbo в базе данных msdb. В следующей таблице описаны столбцы в представлении sysdac_instances.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|instance_id|**uniqueidentifier**|Идентификатор экземпляра DAC.|  
|имя_экземпляра|**sysname**|Имя экземпляра приложения уровня данных, указанное при развертывании DAC.|  
|type_name|**sysname**|Имя DAC, указанное при создании пакета DAC.|  
|type_version|**nvarchar (64)**|Версия DAC, указанная при создании пакета DAC.|  
|description|**nvarchar(4000)**|Описание DAC, записанное при создании пакета DAC.|  
|type_stream|**varbinary(max)**|Битовый поток, который содержит закодированное представление логических объектов, таких как таблицы и представления, содержащихся в DAC.|  
|date_created|**datetime**|Дата и время создания экземпляра DAC.|  
|created_by|**sysname**|Имя входа, создавшее экземпляр DAC.|  
|database_name|**sysname**|Имя базы данных, созданной для экземпляра DAC.|  
  
## <a name="remarks"></a>Примечания  
 DAC включает тип DAC, который представляет собой определение логических объектов уровня данных, используемых приложением, таких как таблицы и представления. Пакет DAC представляет собой файл, используемый для развертывания DAC. Пакет DAC содержит представление всех логических объектов, содержащихся в типе DAC. Пакет DAC может использоваться для развертывания одной или нескольких копий или экземпляров DAC на экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Каждый экземпляр DAC, развернутый одним и тем же пакетом DAC, имеет одинаковый с другими экземплярами тип, но ему присваиваются уникальные имя и идентификатор экземпляра.  
  
## <a name="permissions"></a>Разрешения  
 Требует членства в предопределенной роли сервера sysadmin для просмотра всех столбцов. Члены роли public могут просматривать столбцы instance_name, description и type_version.  
  
## <a name="see-also"></a>См. также  
 [Приложения уровня данных](../../relational-databases/data-tier-applications/data-tier-applications.md)   
 [Представления приложений уровня данных &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/0de01328-d7a6-4677-b7a0-dcd3098c23d4)  
  
  
