---
title: ADCPROP_AUTORECALC_ENUM | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- ADCPROP_AUTORECALC_ENUM
helpviewer_keywords:
- ADCPROP_AUTORECALC_ENUM [ADO]
ms.assetid: ded4f087-87b9-4efa-8026-bde53d3e9e8a
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b00d507a2ddbe596311e16d51a302f4b0dc0dc5
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82760720"
---
# <a name="adcprop_autorecalc_enum"></a>ADCPROP_AUTORECALC_ENUM
Указывает, когда поставщик [мсдаташапе](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) повторно вычисляет статистические и вычисляемые столбцы в иерархическом наборе записей.  
  
 Эти константы используются только с поставщиком **мсдаташапе** и динамическим свойством **"автоматическое перерасчет**" **набора записей** , на которое ссылается [индекс динамического свойства ADO](../../../ado/reference/ado-api/ado-dynamic-property-index.md) и описаны в [службе курсора майкрософт для OLE DB](../../../ado/guide/appendixes/microsoft-cursor-service-for-ole-db-ado-service-component.md) или [службы формирования данных Майкрософт для OLE DB](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) документации.  
  
|Константа|Значение|Описание|  
|--------------|-----------|-----------------|  
|**адрекалкалвайс**|1|По умолчанию. Повторно вычисляется каждый раз, когда поставщик **мсдаташапе** определяет значения, от которых зависит вычисляемые столбцы.|  
|**адрекалкупфронт**|0|Вычисляет только при первоначальном построении иерархического **набора записей**.|  
  
## <a name="adowfc-equivalent"></a>Эквивалент ADO/WFC  
 Эти константы не имеют эквивалентов ADO/WFC.
