---
title: Метод Делетерекорд (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Record::raw_DeleteRecord
- _Record::DeleteRecord
helpviewer_keywords:
- DeleteRecord method [ADO]
ms.assetid: 2726498c-dbd8-4266-983b-ae7d62c39142
author: rothja
ms.author: jroth
ms.openlocfilehash: 550638de710f709616e03cb79afd69f1e533ce9e
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82755316"
---
# <a name="deleterecord-method-ado"></a>Метод DeleteRecord (ADO)
Удаляет сущность, представленную [записью](../../../ado/reference/ado-api/record-object-ado.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
Record.DeleteRecord Source, Async  
```  
  
#### <a name="parameters"></a>Параметры  
 *Источник*  
 Необязательный элемент. **Строковое** значение, содержащее URL-адрес, определяющий сущность (например, файл или каталог) для удаления. Если *Source* не указан или указывает пустую строку, сущность, представленная текущей [записью](../../../ado/reference/ado-api/record-object-ado.md) , удаляется. Если запись является записью коллекции ([RecordType](../../../ado/reference/ado-api/recordtype-property-ado.md) из **адколлектионрекорд**, например каталога), все дочерние элементы (например, подкаталоги) также будут удалены.  
  
 *Async*  
 Необязательный элемент. **Логическое** значение, которое при **значении true**указывает, что операция удаления — асинхронного.  
  
## <a name="remarks"></a>Примечания  
 Операции с объектом, представленным этой **записью** , могут завершиться ошибкой после завершения этого метода. После вызова **Делетерекорд** **запись** должна быть закрыта, поскольку поведение **записи** может стать непредсказуемым в зависимости от того, когда поставщик обновляет **запись** с источником данных.  
  
 Если эта **запись** была получена из [набора записей](../../../ado/reference/ado-api/recordset-object-ado.md), результаты этой операции не будут немедленно отражены в **наборе записей**. Обновите **набор записей** , закрыв и повторно открыв его, либо выполнив метод [запроса](../../../ado/reference/ado-api/requery-method.md) **набора записей** , метод [Update](../../../ado/reference/ado-api/update-method.md) или метод [Resync](../../../ado/reference/ado-api/resync-method.md) .  
  
> [!NOTE]
>  URL-адреса, использующие схему HTTP, автоматически вызывают [поставщик OLE DB Майкрософт для публикации в Интернете](../../../ado/guide/appendixes/microsoft-ole-db-provider-for-internet-publishing.md). Дополнительные сведения см. в разделе [абсолютные и относительные URL-адреса](../../../ado/guide/data/absolute-and-relative-urls.md).  
  
## <a name="applies-to"></a>Применяется к  
 [Объект Record (ADO)](../../../ado/reference/ado-api/record-object-ado.md)  
  
## <a name="see-also"></a>См. также  
 [Метод Delete (коллекция полей ADO)](../../../ado/reference/ado-api/delete-method-ado-fields-collection.md)   
 [Метод Delete (Коллекция параметров ADO)](../../../ado/reference/ado-api/delete-method-ado-parameters-collection.md)   
 [Метод Delete (объект Recordset ADO)](../../../ado/reference/ado-api/delete-method-ado-recordset.md)
