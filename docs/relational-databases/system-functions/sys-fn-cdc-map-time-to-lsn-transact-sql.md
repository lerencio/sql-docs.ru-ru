---
title: sys. fn_cdc_map_time_to_lsn (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.fn_cdc_map_time_to_lsn
- fn_cdc_map_time_to_lsn_TSQL
- sys.fn_cdc_map_time_to_lsn_TSQL
- fn_cdc_map_time_to_lsn
dev_langs:
- TSQL
helpviewer_keywords:
- fn_cdc_map_time_to_lsn
- sys.fn_cdc_map_time_to_lsn
ms.assetid: 6feb051d-77ae-4c93-818a-849fe518d1d4
author: rothja
ms.author: jroth
ms.openlocfilehash: bba5095587b8ddbb4c06d3334ad60e16cb2f5e35
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87395749"
---
# <a name="sysfn_cdc_map_time_to_lsn-transact-sql"></a>sys.fn_cdc_map_time_to_lsn (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Возвращает значение регистрационного номера транзакции в журнале (LSN) из столбца **start_lsn** в системной таблице [CDC. lsn_time_mapping](../../relational-databases/system-tables/cdc-lsn-time-mapping-transact-sql.md) за указанное время. Эту функцию можно использовать для систематического соотнесения диапазонов DateTime с диапазоном номеров LSN, необходимым для функций перечисления отслеживания измененных данных [CDC. fn_cdc_get_all_changes_<capture_instance>](../../relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql.md) и [cdc. fn_cdc_get_net_changes_<](../../relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql.md) capture_instance>для возврата изменений данных в пределах этого диапазона.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sys.fn_cdc_map_time_to_lsn ( '<relational_operator>', tracking_time )  
  
<relational_operator> ::=  
{  largest less than  
 | largest less than or equal  
 | smallest greater than  
 | smallest greater than or equal  
}  
```  
  
## <a name="arguments"></a>Аргументы  
 **'**<relational_operator>**"** {самый крупный меньше \| или равен наименьшему значению меньше чем \| \| наименьшее" больше или равно "}  
 Используется для обнаружения отдельного значения LSN в таблице **CDC. lsn_time_mapping** со связанным **tran_end_time** , который соответствует отношению по сравнению с *tracking_time* значением.  
  
 *relational_operator* имеет тип **nvarchar (30)**.  
  
 *tracking_time*  
 Значение типа datetime для сопоставления. *tracking_time* имеет тип **DateTime**.  
  
## <a name="return-type"></a>Тип возвращаемых данных  
 **binary(10)**  
  
## <a name="remarks"></a>Remarks  
 Чтобы понять, как можно использовать **sys. fn_cdc_map_time_lsn** для преобразования диапазонов DateTime в диапазоны номеров LSN, рассмотрим следующий сценарий. Предположим, что потребителю нужно получать изменения данных ежедневно. То есть потребителю нужны изменения только за определенные сутки. Нижней границей диапазона будет полночь предыдущего дня, не входя в диапазон. Верхней границей будет полночь заданного дня. В следующем примере показано, как функция **sys. fn_cdc_map_time_to_lsn** может быть использована для систематического соотнесения этого диапазона с ДИАПАЗОНОМ номеров LSN, необходимым функциями перечисления для отслеживания измененных данных, для возврата всех изменений в пределах этого диапазона.  
  
 `DECLARE @begin_time datetime, @end_time datetime, @begin_lsn binary(10), @end_lsn binary(10);`  
  
 `SET @begin_time = '2007-01-01 12:00:00.000';`  
  
 `SET @end_time = '2007-01-02 12:00:00.000';`  
  
 `SELECT @begin_lsn = sys.fn_cdc_map_time_to_lsn('smallest greater than', @begin_time);`  
  
 `SELECT @end_lsn = sys.fn_cdc_map_time_to_lsn('largest less than or equal', @end_time);`  
  
 `SELECT * FROM cdc.fn_cdc_get_net_changes_HR_Department(@begin_lsn, @end_lsn, 'all` `');`  
  
 Оператор отношения '`smallest greater than`' используется для ограничения изменений теми, которые произошли после полуночи предыдущего дня. Если несколько записей с разными значениями LSN совместно используют значение **tran_end_time** , определенное как нижняя граница в таблице [CDC. lsn_time_mapping](../../relational-databases/system-tables/cdc-lsn-time-mapping-transact-sql.md) , функция возвратит наименьший номер LSN, гарантируя, что все записи включены. Для верхней границы используется реляционный оператор "", `largest less than or equal to` чтобы гарантировать, что диапазон включает все записи за день, включая значения, равные полуночи, в качестве их **tran_end_time** значений. Если несколько записей с разными значениями LSN совместно используют **tran_end_time** значение, определенное как верхняя граница, функция возвратит максимальный номер LSN, гарантируя, что все записи будут включены.  
  
## <a name="permissions"></a>Разрешения  
 Необходимо быть членом роли **public**.  
  
## <a name="examples"></a>Примеры  
 В следующем примере функция используется `sys.fn_cdc_map_time_lsn` для определения наличия строк в таблице [cdc. lsn_time_mapping](../../relational-databases/system-tables/cdc-lsn-time-mapping-transact-sql.md) со значением **tran_end_time** , которое больше или равно полуночи. Запрос может применяться, например, для определения того, обработал ли процесс отслеживания изменения, зафиксированные до полуночи предыдущего дня, чтобы продолжить извлечение данных изменений для этого дня.  
  
```  
DECLARE @extraction_time datetime, @lsn binary(10);  
SET @extraction_time = '2007-01-01 12:00:00.000';  
SELECT @lsn = sys.fn_cdc_map_time_to_lsn ('smallest greater than or equal', @extraction_time);  
IF @lsn IS NOT NULL  
BEGIN  
<some action>  
END  
```  
  
## <a name="see-also"></a>См. также  
 [CDC. lsn_time_mapping &#40;&#41;Transact-SQL](../../relational-databases/system-tables/cdc-lsn-time-mapping-transact-sql.md)   
 [sys. fn_cdc_map_lsn_to_time &#40;Transact-SQL&#41;](../../relational-databases/system-functions/sys-fn-cdc-map-lsn-to-time-transact-sql.md)   
 [CDC. fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](../../relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql.md)   
 [CDC. fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](../../relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql.md)  
  
  
