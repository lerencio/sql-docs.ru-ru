---
title: Переход к записи a | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- record jumping [ADO]
- jumping to record [ADO]
ms.assetid: 6caf6299-2eea-4d34-9b0e-b75aab07b740
author: rothja
ms.author: jroth
ms.openlocfilehash: eca1d1646721ea34d4ce075a882bde95b3c407a3
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82757770"
---
# <a name="jumping-to-a-record"></a>Переход к записи
Метод [Move](../../../ado/reference/ado-api/move-method-ado.md) позволяет перемещаться вперед или назад в **наборе** записей по заданному числу записей с помощью следующего синтаксиса:  
  
```  
oRs.Move NumRecords, Start  
```  
  
## <a name="remarks"></a>Remarks  
 Метод **Move** поддерживается для всех объектов **Recordset** .  
  
 Если аргумент *нумрекордс* больше нуля, текущее расположение записи перемещается вперед (к концу **набора записей**). Если значение *нумрекордс* меньше нуля, текущее расположение записи перемещается назад (в направлении начала **набора записей**).  
  
 Если при вызове **Move** положение текущей записи перемещается в точку до первой записи, ADO устанавливает текущую запись в позицию перед первой записью в **наборе записей** (**BOF** имеет **значение true**). Попытка перемещения назад, если свойство **BOF** уже имеет **значение true** , приводит к ошибке.  
  
 Если при вызове **Move** положение текущей записи перемещается в точку после последней записи, ADO устанавливает текущую запись в позицию после последней записи в **наборе записей** (значение**EOF** равно **true**). Попытка перемещения вперед, если свойство **EOF** уже имеет **значение true** , приводит к ошибке.  
  
 Вызов метода **Move** из пустого объекта **Recordset** приводит к ошибке.  
  
 Если передать закладку в аргументе *Start* , то перемещение будет относиться к записи с этой закладкой, предполагая, что объект **набора записей** поддерживает закладки. Закладка получается с помощью свойства [Bookmark](../../../ado/reference/ado-api/bookmark-property-ado.md) . Если значение не указано, то перемещение отсчитывается относительно текущей записи.  
  
 Если свойство **CacheSize** используется для локального кэширования записей от поставщика, передача аргумента *нумрекордс* , который перемещает текущую запись за пределы текущей группы кэшированных записей, заставляет ADO получить новую группу записей, начиная с целевой записи. Свойство **CacheSize** определяет размер вновь полученной группы, а конечную запись — первую извлеченную запись.
