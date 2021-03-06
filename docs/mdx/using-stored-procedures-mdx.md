---
title: Использование хранимых процедур (многомерные выражения) | Документация Майкрософт
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: c7cc3a7ba79b15b0eee36ac6907013673a5b7bf9
ms.sourcegitcommit: 205de8fa4845c491914902432791bddf11002945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "86971492"
---
# <a name="using-stored-procedures-mdx"></a>Использование хранимых процедур (многомерные выражения)


  Возможности служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и многомерных выражений можно расширить путем записи хранимых процедур платформы .NET или определяемых пользователем функций. Дополнительные сведения см. в разделе [ADOMD.NET Server Programming](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-server/adomd-net-server-programming) .  
  
 При обращении или вызове хранимой процедуры необходимо указать имя функции и круглые скобки. Внутри скобок можно указать выражения (или аргументы), представляющие собой данные, передаваемые в виде параметров. Вызывая функцию, необходимо указать значения аргументов для всех параметров, причем в той последовательности, в которой параметры перечислены в определении пользовательской функции.  
  
 В следующем примере запроса предполагается, что на сервере служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] зарегистрирована сборка SampleAssembly:  
  
```  
SELECT SampleAssembly.RandomSample([Geography].[State-Province].Members, 5) on ROWS,   
[Date].[Calendar].[Calendar Year] on COLUMNS  
FROM [Adventure Works]  
WHERE [Measures].[Reseller Freight Cost]  
```  
  
> [!NOTE]  
>  *Хранимая процедура* — это терминология, используемая в [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] для этих типов функций. Более ранние версии [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] вызывали эти типы функций в качестве *определяемых пользователем функций*.  
  
## <a name="types-of-stored-procedures"></a>Типы хранимых процедур  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] поддерживает сборки COM и CLR. Рекомендуется использовать сборки CLR, поскольку для них имеются расширенные механизмы защиты. Если на сервере установлена электронная таблица Microsoft Office Excel, можно также использовать функции Excel.  
  
> [!NOTE]  
>  COM-сборки Microsoft Visual Basic for Applications (VBA) регистрируются автоматически.  
  
## <a name="see-also"></a>См. также  
 [Функции &#40;синтаксиса многомерных выражений&#41;](../mdx/functions-mdx-syntax.md)  
  
  
