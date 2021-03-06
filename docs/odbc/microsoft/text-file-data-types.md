---
title: Типы данных текстовых файлов | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- text file driver [ODBC], data types
- ODBC desktop database drivers [ODBC], text file driver
- desktop database drivers [ODBC], text file driver
- text file data types [ODBC]
- Jet-based ODBC drivers [ODBC], text file driver
ms.assetid: e113112e-ae42-469e-8e4b-a365a10d9071
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 7864dc81eaa3dd37f3d0053b2329c8842e445c8d
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81302662"
---
# <a name="text-file-data-types"></a>Типы данных текстовых файлов
В следующей таблице показано, как типы текстовых данных сопоставляются с типами данных ODBC SQL. Обратите внимание, что текстовый драйвер ODBC поддерживает не все типы данных ODBC SQL.  
  
|Тип данных text|Тип данных ODBC|  
|--------------------|--------------------|  
|CHAR|SQL_VARCHAR|  
|DATETIME|SQL_TIMESTAMP|  
|FLOAT|SQL_DOUBLE|  
|INTEGER|SQL_INTEGER|  
|лонгчар|SQL_LONGVARCHAR|  
  
> [!NOTE]  
>  **SQLGetTypeInfo** возвращает типы данных ODBC. Все преобразования в приложении D *Справочника программиста ODBC* поддерживаются для типов данных SQL, перечисленных в предыдущей таблице.  
  
 В следующей таблице приведены ограничения для текстовых типов данных.  
  
|Тип данных|Описание|  
|---------------|-----------------|  
|CHAR|Создание столбца CHAR нулевой или неуказанной длины фактически возвращает 255-разрядный столбец.<br /><br /> В файлах с разделителями столбец типа CHAR может иметь или не содержать двойные кавычки в начале и конце; в файлах фиксированной длины двойные кавычки не используются в качестве разделителей.|  
|DATETIME|MM-ДД-гг (например, 01-17-92)<br /><br /> Ммм-дд-гг (например, Янв-17-92)<br /><br /> ДД-ммм-гг (например, 17-Янв-92)<br /><br /> ГГГГ-мм-дд (например, 1992-01-17)<br /><br /> ГГГГ-МММ-ДД (например, 1992-Янв-17)<br /><br /> В таблице нельзя использовать смешанные разделители дат.<br /><br /> Текст ISAM форматирует поле DATETIME в США или Европейский формат в зависимости от региональных настроек на панели управления Windows.|  
|FLOAT|Максимальная ширина включает знак и десятичную точку. В файле Schema. ini ширина обозначается следующим образом:<br /><br /> 14,083 имеет ширину FLOAT 6<br /><br /> -14,083 — ПЛАВАЮЩая ширина 7<br /><br /> + 14,083 — ПЛАВАЮЩая ширина 7<br /><br /> 14083. имеет ширину FLOAT 6<br /><br /> ODBC всегда возвращает 8 для столбцов с плавающей запятой.<br /><br /> Столбцы с плавающей запятой также могут быть в экспоненциальном представлении, например:<br /><br /> -3.04 e + 2 имеет ширину float 8<br /><br /> 25E4 имеет ширину float 4<br /><br /> **Примечание** . Десятичная и экспоненциальная нотация не могут быть смешанными в столбце.<br /><br /> Значения NULL представлены пустой строкой в файлах фиксированной длины и пропускаются в файлах с разделителями.<br /><br /> Данные с плавающей запятой могут быть дополнены начальными пробелами.|  
|INTEGER|Допустимые значения для ЦЕЛОЧИСЛЕНных столбцов — от 32767 до-32766.<br /><br /> В файле Schema. ini ширина обозначается следующим образом:<br /><br /> 14083 — ЦЕЛОЧИСЛЕНная ширина 5<br /><br /> 0 — ЦЕЛОЧИСЛЕНная ширина 1<br /><br /> ODBC всегда возвращает 4 для ЦЕЛОЧИСЛЕНных столбцов.<br /><br /> Максимальная ширина включает знак. Максимальная ширина ЦЕЛОЧИСЛЕНного столбца составляет 11, хотя ширина может быть больше из-за пустых значений, допустимых в таблицах фиксированного формата.|  
|лонгчар|Теоретическим ограничением для ширины столбца ЛОНГЧАР в таблице с фиксированной длиной или с разделителями является 65500K. Чаще всего текст ISAM обеспечивает надежную поддержку до 32 КБ.|  
  
 Дополнительные ограничения для типов данных можно найти в [ограничениях типа данных](../../odbc/microsoft/data-type-limitations.md).
