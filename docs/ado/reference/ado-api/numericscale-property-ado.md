---
title: Свойство NumericScale (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Parameter::NumericScale
- Field20::NumericScale
helpviewer_keywords:
- NumericScale property [ADO]
ms.assetid: 29a02992-64be-4fcd-be13-445cba205893
author: rothja
ms.author: jroth
ms.openlocfilehash: 38a44aeac4a2238e7d0087ec458df9f77086aa0c
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87242634"
---
# <a name="numericscale-property-ado"></a>Свойство NumericScale (ADO)
Указывает масштаб числовых значений в объекте [параметра](../../../ado/reference/ado-api/parameter-object.md) или [поля](../../../ado/reference/ado-api/field-object.md) .  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает значение **типа Byte** , указывающее количество десятичных разрядов, к которым будут разрешены числовые значения.  
  
## <a name="remarks"></a>Remarks  
 Используйте свойство **NumericScale** , чтобы определить, сколько цифр справа от десятичной запятой будет использоваться для представления значений числового **параметра** или объекта **поля** .  
  
 Для объектов **параметров** свойство **NumericScale** доступно для чтения и записи.  
  
 Для объекта **field** **NumericScale** обычно доступен только для чтения. Однако для новых объектов **field** , добавленных к коллекции [Fields](../../../ado/reference/ado-api/fields-collection-ado.md) [записи](../../../ado/reference/ado-api/record-object-ado.md), **NumericScale** доступен только для чтения и записи только после того, как было указано свойство [value](../../../ado/reference/ado-api/value-property-ado.md) для **поля** и поставщик данных успешно добавил новое **поле** , вызвав метод [Update](../../../ado/reference/ado-api/update-method.md) коллекции [Fields](../../../ado/reference/ado-api/fields-collection-ado.md) .  
  
## <a name="applies-to"></a>Применение  

:::row:::
    :::column:::
        [Объект Field](../../../ado/reference/ado-api/field-object.md)  
    :::column-end:::
    :::column:::
        [Объект Parameter](../../../ado/reference/ado-api/parameter-object.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>См. также:  
 [Пример свойств NumericScale и Precision (Visual Basic)](../../../ado/reference/ado-api/numericscale-and-precision-properties-example-vb.md)   
 [Пример свойств NumericScale и Precision (Visual c++)](../../../ado/reference/ado-api/numericscale-and-precision-properties-example-vc.md)   
 [Свойство Precision (ADO)](../../../ado/reference/ado-api/precision-property-ado.md)
