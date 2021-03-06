---
title: Параметры проекта (сопоставление типов) (SybaseToSQL) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 2698fb3a-f9e6-4e04-94e0-dad289d7ed0a
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: d7b16bdf3717fa14f91af41663cbd65365eac52a
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "68028659"
---
# <a name="project-settings-type-mapping-sybasetosql"></a>Параметры проекта (сопоставление типов) (SybaseToSQL)
Страница Сопоставление типов диалогового окна **Параметры проекта** содержит параметры, которые настраивают, каким способом SSMA преобразует адаптивные серверные типы данных SYBASE ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ASE) в типы данных.  
  
Страница Сопоставление типов доступна в диалоговых окнах **Параметры проекта** и **Параметры проекта по умолчанию** .  
  
-   Чтобы указать параметры сопоставления типов для всех будущих проектов SSMA, в меню **Сервис** выберите **Параметры проекта по умолчанию**, выберите тип проекта миграции, для которого необходимо просмотреть или изменить параметры в раскрывающемся списке **версия целевого объекта миграции** , а затем выберите **Сопоставление типов** в нижней части левой панели.  
  
-   Чтобы указать параметры для текущего проекта, в меню **Сервис** выберите пункт **Параметры проекта**, а затем выберите **Сопоставление типов** в нижней части левой панели.  
  
## <a name="options"></a>Параметры  
**Тип источника**  
Сопоставленный тип данных ASE.  
  
**Тип целевого объекта**  
Целевой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] тип данных для указанного типа данных ASE.  
  
См. таблицу в следующем разделе для сопоставления типов SSMA по умолчанию для Sybase.  
  
**Добавление**  
Нажмите, чтобы добавить тип данных в список сопоставления.  
  
**Edit** (Изменение)  
Нажмите, чтобы изменить выбранный тип данных в списке сопоставление.  
  
**Удалить**  
Нажмите, чтобы удалить выбранное сопоставление типа данных из списка сопоставления.  
  
**По умолчанию**  
Нажмите, чтобы сбросить список сопоставления типов к значениям по умолчанию SSMA.  
  
## <a name="default-type-mapping"></a>Сопоставление типов по умолчанию  
В следующей таблице содержится сопоставление типов по умолчанию между ASE [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и типами данных.  
  
|Тип данных ASE|Тип данных SQL Server|  
|-----------------|------------------------|  
|**bigint**|**bigint**|  
|**binary**|**binary**|  
|**двоичный\*файл [.. 8000]**|**Binary [\*]**|  
|**двоичный [8001.\*.]**|**varbinary(max)**|  
|**bit**|**bit**|  
|**char**|**char**|  
|**char varying**|**varchar**|  
|**различные знаки [\*.. 8000]**|**varchar [\*]**|  
|**изменение типа char [8001.\*.]**|**varchar(max)**|  
|**Char [\*.. 8000]**|**Char [\*]**|  
|**Char [8001..\*;]**|**varchar(max)**|  
|**символов**|**char**|  
|**character varying**|**varchar**|  
|**Разное символов\*[.. 8000]**|**varchar [\*]**|  
|**разное начертание [8001\*..]**|**varchar(max)**|  
|**символ [\*.. 8000]**|**Char [\*]**|  
|**символ [8001..\*]**|**varchar(max)**|  
|**date**|**date**|  
|**datetime**|**datetime2 [3]**|  
|**уменьшение**|**decimal**|  
|**Dec [\*.. \*]**|**Decimal [\*]**|  
|**Dec [\*.. \*][\*.. \*]**|**Decimal [\*] [\*]**|  
|**decimal**|**decimal**|  
|**Decimal [\*.. \*]**|**Decimal [\*]**|  
|**Decimal [\*.. \*][\*.. \*]**|**Decimal [\*] [\*]**|  
|**Двойная точность**|**float [53]**|  
|**float**|**float [53]**|  
|**float [\*.. 15**|**float [24]**|  
|**float [16..\*]**|**float [53]**|  
|**image**|**image**|  
|**int**|**int**|  
|**integer**|**int**|  
|**лонгсиснаме**|**nvarchar [255]**|  
|**money**|**money**|  
|**Национальный знак**|**nchar**|  
|**Национальный знак [\*.. 4000]**|**nchar [\*]**|  
|**разные национальные знаки**|**nvarchar**|  
|**Национальный символ [\*.. 4000]**|**nvarchar [\*]**|  
|**Национальный символ [4001..\*]**|**nvarchar(max)**|  
|**Национальный символ [4001..\*]**|**nvarchar(max)**|  
|**Национальный символ**|**nchar**|  
|**Национальный символ [\*.. 4000]**|**nchar [\*]**|  
|**Национальный символ [4001..\*]**|**nvarchar(max)**|  
|**изменение национального алфавита**|**nvarchar**|  
|**Национальный символ, с\*разностью [.. 4000]**|**nvarchar [\*]**|  
|**Национальный символ, Разное [4001\*..]**|**nvarchar(max)**|  
|**Национальный varchar**|**nvarchar**|  
|**Национальный varchar [\*.. 4000]**|**nvarchar [\*]**|  
|**Национальный varchar [4001..\*]**|**nvarchar(max)**|  
|**nchar**|**nchar**|  
|**Разное изменение типа nchar**|**nvarchar**|  
|**изменение типа nchar\*[.. 4000]**|**nvarchar [\*]**|  
|**изменение типа nchar [4001.\*.]**|**nvarchar(max)**|  
|**nchar [\*.. 4000]**|**nchar [\*]**|  
|**nchar [4001..\*]**|**nvarchar(max)**|  
|**numeric**|**numeric**|  
|**numeric [\*.. \*]**|**numeric [\*]**|  
|**numeric [\*.. \*][\*.. \*]**|**numeric [\*] [\*]**|  
|**nvarchar**|**nvarchar**|  
|**nvarchar [\*.. 4000]**|**nvarchar [\*]**|  
|**nvarchar [4001..\*]**|**nvarchar(max)**|  
|**real**|**float [24]**|  
|**smalldatetime**|**smalldatetime**|  
|**smallint**|**smallint**|  
|**smallmoney**|**smallmoney**|  
|**sysname**|**nvarchar [128]**|  
|**sysname [\*.. \*]**|**nvarchar [255]**|  
|**text**|**text**|  
|**time**|**время [3]**|  
|**timestamp**|**rowversion**|  
|**tinyint**|**tinyint**|  
|**уничар**|**nchar**|  
|**уничар**|**nvarchar**|  
|**уничар [\*.. 4000]**|**nvarchar [\*]**|  
|**уничар [4001..\*]**|**nvarchar(max)**|  
|**уничар [\*.. 4000]**|**nchar [\*]**|  
|**уничар [4001..\*]**|**nvarchar(max)**|  
|**унитекст**|**nvarchar(max)**|  
|**униварчар**|**nvarchar**|  
|**униварчар [\*.. 4000]**|**nvarchar [\*]**|  
|**униварчар [4001..\*]**|**nvarchar(max)**|  
|**bigint без знака**|**числовой [20] [0]**|  
|**unsigned int**|**bigint**|  
|**неподписанный smallint**|**int**|  
|**неподписанный tinyint**|**tinyint**|  
|**varbinary**|**varbinary**|  
|**varbinary [\*.. 8000]**|**varbinary [\*]**|  
|**varbinary [8001..\*]**|**varbinary(max)**|  
|**varchar**|**varchar**|  
|**varchar [\*.. 8000]**|**varchar [\*]**|  
|**varchar [8001..\*]**|**varchar(max)**|  
  
