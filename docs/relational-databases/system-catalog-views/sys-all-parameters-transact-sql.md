---
title: sys. all_parameters (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- all_parameters_TSQL
- sys.all_parameters
- all_parameters
- sys.all_parameters_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.all_parameters catalog view
ms.assetid: eecbb68e-9b4c-4243-94e2-8096a9cc7892
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: d77c2eb7338b0efaad2719d96fe8ecb5dc51fee2
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2020
ms.locfileid: "86006327"
---
# <a name="sysall_parameters-transact-sql"></a>sys.all_parameters (Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Содержит все параметры, относящиеся к пользовательским или системным объектам.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|Идентификатор объекта, которому принадлежит этот параметр.|  
|**name**|**sysname**|Имя параметра. Уникален в пределах объекта. Если объект является скалярной функцией, именем параметра будет пустая строка в строке, представляющей возвращаемое значение.|  
|**parameter_id**|**int**|Идентификатор параметра. Уникален в пределах объекта. Если объект является скалярной функцией, **parameter_id** = 0 представляет возвращаемое значение.|  
|**system_type_id**|**tinyint**|Идентификатор системного типа параметра.|  
|**user_type_id**|**int**|Определенный пользователем идентификатор типа параметра.<br /><br /> Чтобы вернуть имя типа, присоединитесь к представлению каталога [sys. types](../../relational-databases/system-catalog-views/sys-types-transact-sql.md) в этом столбце.|  
|**max_length**|**smallint**|Максимальная длина параметра в байтах.<br /><br /> -1 = тип данных столбца — **varchar (max)**, **nvarchar (max)**, **varbinary (max)** или **XML**.|  
|**precision**|**tinyint**|Точность параметра, если он является числовым; иначе — 0.|  
|**масштаб**|**tinyint**|Масштаб числового параметра, если он является числовым; иначе — 0.|  
|**is_output**|**bit**|1 = выходной параметр (или возвращаемый); иначе — 0.|  
|**is_cursor_ref**|**bit**|1 = параметр является ссылкой на курсор.|  
|**has_default_value**|**bit**|1 = параметр имеет значение по умолчанию.<br /><br /> В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживаются значения по умолчанию для объектов среды CLR в данном представлении каталога, поэтому в данном столбце всегда будет содержаться значение 0 для объектов языка [!INCLUDE[tsql](../../includes/tsql-md.md)]. Чтобы просмотреть значение параметра по умолчанию в [!INCLUDE[tsql](../../includes/tsql-md.md)] объекте, выполните запрос к столбцу **определения** представления каталога [sys. sql_modules](../../relational-databases/system-catalog-views/sys-sql-modules-transact-sql.md) или используйте системную функцию [OBJECT_DEFINITION](../../t-sql/functions/object-definition-transact-sql.md) .|  
|**is_xml_document**|**bit**|1 = содержимое является готовым XML-документом.<br /><br /> 0 = содержимое является фрагментом документа, или тип данных столбца не является **XML**.|  
|**default_value**|**sql_variant**|Если **has_default_value** равен 1, значение этого столбца равно значению по умолчанию для параметра; в противном случае значение NULL.|  
|**xml_collection_id**|**int**|Идентификатор коллекции XML-схем, используемый для проверки параметра.<br /><br /> Ненулевое значение, если тип данных параметра — **XML** , а XML-код типизирован.<br /><br /> 0 = нет коллекций XML-схем, или тип параметра не XML.|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>См. также  
 [Представления каталога объектов &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Представления каталога &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Запросы к системному каталогу SQL Server вопросы и ответы](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)   
 [sys. parameters &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/sys-parameters-transact-sql.md)   
 [sys.system_parameters &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-system-parameters-transact-sql.md)  
  
  
