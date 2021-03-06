---
title: '&gt;= (Больше или равно) (расширения интеллектуального анализа данных) | Документация Майкрософт'
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: f4dfae8259c1ea9379500d426ce1c8ac22762068
ms.sourcegitcommit: 205de8fa4845c491914902432791bddf11002945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "86971662"
---
# <a name="gt-greater-than-or-equal-to-dmx"></a>&gt;= (Больше или равно) (расширения интеллектуального анализа данных)
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  Выполняет операцию сравнения с целью определения, является ли одно выражение больше второго выражения расширений интеллектуального анализа данных или равным ему.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
DMX_Expression >= DMX_Expression  
```  
  
#### <a name="parameters"></a>Параметры  
 *DMX_Expression*  
 Допустимое выражение расширений интеллектуального анализа данных.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Логическое значение равно TRUE в случае, если оба аргумента не равны NULL, и значение первого аргумента больше значения второго аргумента или равно ему. Логическое значение равно FALSE, если оба аргумента не равны NULL, и первый аргумент имеет значение меньшее, чем второй. Логическое значение равно NULL, если один или оба аргумента имеют значение NULL.  
  
## <a name="see-also"></a>См. также  
 [Операторы сравнения &#40;&#41;расширений интеллектуального анализа данных](../dmx/operators-comparison.md)   
 [Ссылки на операторы расширений интеллектуального анализа данных &#40;DMX&#41;](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [Операторы &#40;&#41;расширений интеллектуального анализа данных](../dmx/operators-dmx.md)  
  
  
