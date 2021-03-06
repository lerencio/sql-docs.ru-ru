---
title: Справочник по операторам расширений интеллектуального анализа данных (DMX) | Документация Майкрософт
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 60271f810de7d577bebdaac4ed0ceb6e48c08d68
ms.sourcegitcommit: 205de8fa4845c491914902432791bddf11002945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "86971790"
---
# <a name="data-mining-extensions-dmx-operator-reference"></a>Ссылка оператора расширений интеллектуального анализа данных
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  Язык расширений интеллектуального анализа данных в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] поддерживает арифметические, операторы присваивания, сравнения, логических и унарных операторов. В следующей таблице перечислены операторы, поддерживаемые расширениями интеллектуального анализа данных.  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[+ &#40;Добавление&#41; &#40;расширений интеллектуального анализа данных&#41;](../dmx/add-dmx.md)|Арифметический оператор, складывающий два числа.|  
|[-&#40;вычитание&#41; &#40;расширений интеллектуального анализа данных&#41;](../dmx/subtract-dmx.md)|Арифметический оператор, вычитающий одно число из другого.|  
|[&#42; &#40;умножение&#41; &#40;DMX&#41;](../dmx/multiply-dmx.md)|Арифметический оператор, умножающий одно число на другое.|  
|[&#40;разделение&#41; &#40;DMX&#41;](../dmx/divide-dmx.md)|Арифметический оператор, делящий одно число на другое.|  
|[&#60; &#40;меньше&#41; &#40;&#41;расширений интеллектуального анализа данных](../dmx/less-than-dmx.md)|Оператор сравнения. Для аргументов, значения которых отличны от NULL, возвращает TRUE, если значение аргумента слева меньше, чем значение аргумента справа; в противном случае возвращает FALSE. Если один или оба аргумента имеют значение NULL, оператор возвращает значение NULL.|  
|[&#62; &#40;больше&#41; &#40;расширений интеллектуального анализа данных&#41;](../dmx/greater-than-dmx.md)|Оператор сравнения. Для аргументов, значения которых отличны от NULL, возвращает TRUE, если значение аргумента слева больше, чем значение аргумента справа; в противном случае возвращает FALSE. Если один или оба аргумента имеют значение NULL, оператор возвращает значение NULL.|  
|[= &#40;равно&#41; &#40;DMX&#41;](../dmx/equal-to-dmx.md)|Оператор сравнения. Для аргументов, значения которых отличны от NULL, возвращает TRUE, если значение аргумента слева равно значению аргумента справа; в противном случае возвращает FALSE. Если один или оба аргумента имеют значение NULL, оператор возвращает значение NULL.|  
|[&#60;&#62; &#40;не равно&#41; &#40;расширений интеллектуального анализа данных&#41;](../dmx/not-equal-to-dmx.md)|Оператор сравнения. Для аргументов, значения которых отличны от NULL, возвращает TRUE, если значение аргумента слева не равно значению аргумента справа; в противном случае возвращает FALSE. Если один или оба аргумента имеют значение NULL, оператор возвращает значение NULL.|  
|[&#60;= &#40;меньше или равно&#41; &#40;DMX&#41;](../dmx/less-than-or-equal-to-dmx.md)|Оператор сравнения. Для аргументов, значения которых отличны от NULL, возвращает TRUE, если значение аргумента слева равно значению аргумента справа или меньше него; в противном случае возвращает FALSE. Если один или оба аргумента имеют значение NULL, оператор возвращает значение NULL.|  
|[&#62;= &#40;больше или равно&#41; &#40;расширений интеллектуального анализа данных&#41;](../dmx/greater-than-or-equal-to-dmx.md)|Оператор сравнения. Для аргументов, значения которых отличны от NULL, возвращает TRUE, если значение аргумента слева равно значению аргумента справа или больше него; в противном случае возвращает FALSE. Если один или оба аргумента имеют значение NULL, оператор возвращает значение NULL.|  
|[И &#40;&#41;РАСШИРЕНИЙ ИНТЕЛЛЕКТУАЛЬНОГО АНАЛИЗА ДАННЫХ](../dmx/and-dmx.md)|Логический оператор, выполняющий конъюнкцию (умножение) двух числовых выражений.|  
|[НЕ &#40;&#41;РАСШИРЕНИЙ ИНТЕЛЛЕКТУАЛЬНОГО АНАЛИЗА ДАННЫХ](../dmx/not-dmx.md)|Логический оператор, выполняющий отрицание числового выражения.|  
|[ИЛИ &#40;&#41;РАСШИРЕНИЙ ИНТЕЛЛЕКТУАЛЬНОГО АНАЛИЗА ДАННЫХ](../dmx/or-dmx.md)|Логический оператор, выполняющий дизъюнкцию двух числовых выражений.|  
|[+ &#40;положительное&#41; &#40;расширений интеллектуального анализа данных&#41;](../dmx/positive-dmx.md)|Унарный оператор, возвращающий положительное значение числового выражения.|  
|[-&#40;отрицательное&#41; &#40;расширений интеллектуального анализа данных&#41;](../dmx/negative-dmx.md)|Унарный оператор, возвращающий отрицательное значение числового выражения.|  
|[Двойная косая черта &#40;комментарий&#41; &#40;DMX&#41;](../dmx/double-slash-comment-dmx.md)|Указывает строку текста, которая не должна выполняться службами [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]. Комментарии можно вложить в инструкцию расширений интеллектуального анализа данных, включить их в конец строки кода или вставить их отдельной строкой.|  
|[--&#40;комментарий&#41; &#40;&#41; сводные данные расширений интеллектуального анализа данных](../dmx/comment-dmx-summary.md)|Указывает строку текста, которая не должна выполняться службами [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]. Комментарии можно вложить в инструкцию расширений интеллектуального анализа данных, включить их в конец строки кода или вставить их отдельной строкой.|  
|[Косая черта-звездочка &#40;комментарии&#41; &#40;DMX&#41;](../dmx/slash-star-comment-dmx.md)|Указывает строку текста, которая не должна выполняться службами [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]. Комментарии можно вложить в инструкцию расширений интеллектуального анализа данных, включить их в конец строки кода или вставить их отдельной строкой.|  
  
## <a name="see-also"></a>См. также  
 [Расширения интеллектуального анализа данных &#40;Справочник по функциям DMX&#41;](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Расширения интеллектуального анализа данных &#40;Справочник по DMX&#41;](../dmx/data-mining-extensions-dmx-reference.md)   
 [Расширения интеллектуального анализа данных &#40;Справочник по инструкции DMX&#41;](../dmx/data-mining-extensions-dmx-statements.md)   
 [Расширения интеллектуального анализа данных &#40;синтаксические обозначения&#41; DMX](../dmx/data-mining-extensions-dmx-syntax-conventions.md)   
 [Расширения интеллектуального анализа данных &#40;синтаксические&#41; DMX-элементы](../dmx/data-mining-extensions-dmx-syntax-elements.md)   
 [Операторы &#40;&#41;расширений интеллектуального анализа данных](../dmx/operators-dmx.md)  
  
  
