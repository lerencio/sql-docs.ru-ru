---
title: Использование массивов параметров | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- arrays of parameter values [ODBC]
- parameter arrays [ODBC]
ms.assetid: 5a28be88-e171-4f5b-bf4d-543c4383c869
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b584dc3d635e9fa8ce3228e4e89b0f24451fe165
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81306805"
---
# <a name="using-arrays-of-parameters"></a>Использование массивов параметров
Чтобы использовать массивы параметров, приложение вызывает **SQLSetStmtAttr** с аргументом *атрибута* SQL_ATTR_PARAMSET_SIZE, чтобы указать количество наборов параметров. Он вызывает **SQLSetStmtAttr** с аргументом *атрибута* SQL_ATTR_PARAMS_PROCESSED_PTR, чтобы указать адрес переменной, в которой драйвер может вернуть количество обработанных наборов параметров, включая наборы ошибок. Он вызывает **SQLSetStmtAttr** с аргументом *атрибута* SQL_ATTR_PARAM_STATUS_PTR для указания на массив, в котором возвращаются сведения о состоянии для каждой строки значений параметров. Драйвер сохраняет эти адреса в структуре, которая поддерживается для инструкции.  
  
> [!NOTE]  
>  В ODBC 2. *x*, **SQLParamOptions** был вызван для указания нескольких значений для параметра. В ODBC 3. *x*, вызов **SQLParamOptions** был заменен вызовами метода **SQLSetStmtAttr** для задания атрибутов SQL_ATTR_PARAMSET_SIZE и SQL_ATTR_PARAMS_PROCESSED_ARRAY.  
  
 Перед выполнением инструкции приложение задает значение каждого элемента в каждом привязанном массиве. При выполнении инструкции драйвер использует сохраненные сведения для получения значений параметров и отправки их в источник данных. Если это возможно, драйвер должен отправить эти значения в виде массивов. Хотя использование массивов параметров лучше всего реализуется путем выполнения инструкции SQL со всеми параметрами в массиве с одним вызовом к источнику данных, эта возможность в настоящее время недоступна в СУБД. Однако драйверы могут имитировать его, выполняя инструкцию SQL несколько раз, каждый из которых имеет один набор параметров.  
  
 Прежде чем приложение будет использовать массивы параметров, необходимо убедиться, что они поддерживаются драйверами, используемыми приложением. Это можно сделать двумя способами.  
  
-   Используйте только драйверы, известные для поддержки массивов параметров. Приложение может жестко кодировать имена этих драйверов, или пользователь может дать инструкции использовать только эти драйверы. Пользовательские приложения и вертикальные приложения обычно используют ограниченный набор драйверов.  
  
-   Проверка поддержки массивов параметров во время выполнения. Драйвер поддерживает массивы параметров, если можно присвоить атрибуту инструкции SQL_ATTR_PARAMSET_SIZE значение больше 1. Универсальные приложения и вертикальные приложения обычно проверяют поддержку массивов параметров во время выполнения.  
  
 Доступность количества строк и результирующих наборов в параметризованном выполнении можно определить с помощью вызова **SQLGetInfo** с параметрами SQL_PARAM_ARRAY_ROW_COUNTS и SQL_PARAM_ARRAY_SELECTS. Для инструкций **INSERT**, **Update**и **Delete** параметр SQL_PARAM_ARRAY_ROW_COUNTS указывает, доступны ли отдельные строки (по одному для каждого набора параметров) (SQL_PARC_BATCH) или сведены ли счетчики строк в одну (SQL_PARC_NO_BATCH). Для инструкций **SELECT** параметр SQL_PARAM_ARRAY_SELECTS указывает, доступен ли результирующий набор для каждого набора параметров (SQL_PAS_BATCH) или доступен ли только один результирующий набор (SQL_PAS_NO_BATCH). Если драйвер не разрешает выполнение инструкций результирующего набора с массивом параметров, SQL_PARAM_ARRAY_SELECTS возвращает SQL_PAS_NO_SELECT. Это зависит от источника данных, можно ли использовать массивы параметров с другими типами инструкций, особенно потому, что в этих инструкциях используются параметры, относящиеся к источнику данных, и не должны следовать грамматике ODBC SQL.  
  
 Массив, на который указывает атрибут инструкции SQL_ATTR_PARAM_OPERATION_PTR, можно использовать для пропуска строк параметров. Если элемент массива имеет значение SQL_PARAM_IGNORE, набор параметров, соответствующих этому элементу, исключается из вызова **SQLExecute** или **SQLExecDirect** . Массив, на который указывает атрибут SQL_ATTR_PARAM_OPERATION_PTR, выделяется и заполняется приложением и считывается драйвером. Если в качестве входных параметров используются выбранные строки, значения массива состояния строки можно использовать в массиве операций с параметрами.  
  
## <a name="error-processing"></a>Обработка ошибок  
 Если при выполнении инструкции возникает ошибка, то функция выполнения возвращает ошибку и присваивает переменной номер строки номер строки, содержащей ошибку. Это зависит от источника данных, выполняются ли все строки, за исключением набора ошибок, или от того, выполняются ли все строки перед (но не после). Так как он обрабатывает наборы параметров, драйвер устанавливает буфер, заданный атрибутом SQL_ATTR_PARAMS_PROCESSED_PTR, равным номеру строки, обрабатываемой в данный момент. Если выполняются все наборы, кроме набора ошибок, драйвер устанавливает этот буфер в SQL_ATTR_PARAMSET_SIZE после обработки всех строк.  
  
 Если задан атрибут инструкции SQL_ATTR_PARAM_STATUS_PTR, **SQLExecute** или **SQLExecDirect** возвращает *массив состояния параметра,* который предоставляет состояние каждого набора параметров. Массив состояния параметра выделяется приложением и заполняется драйвером. Его элементы указывают, успешно ли выполнена инструкция SQL для строки параметров или произошла ошибка при обработке набора параметров. Если произошла ошибка, драйвер задает соответствующее значение в массиве состояния параметра равным SQL_PARAM_ERROR и возвращает SQL_SUCCESS_WITH_INFO. Приложение может проверить массив состояния, чтобы определить, какие строки были обработаны. С помощью номера строки приложение часто может исправить ошибку и возобновить обработку.  
  
 Способ использования массива состояния параметра определяется параметрами SQL_PARAM_ARRAY_ROW_COUNTS и SQL_PARAM_ARRAY_SELECTS, возвращаемыми вызовом **SQLGetInfo**. Для инструкций **INSERT**, **Update**и **Delete** массив состояния параметра заполняется сведениями о состоянии, если SQL_PARC_BATCH возвращается для SQL_PARAM_ARRAY_ROW_COUNTS, но не при возвращении SQL_PARC_NO_BATCH. Для инструкций **SELECT** массив состояния параметра заполняется, если для SQL_PARAM_ARRAY_SELECT возвращается SQL_PAS_BATCH, но не возвращается значение SQL_PAS_NO_BATCH или SQL_PAS_NO_SELECT.  
  
## <a name="data-at-execution-parameters"></a>Параметры данных при выполнении  
 Если любое из значений в массиве length/индикаторов SQL_DATA_AT_EXEC или результат макроса SQL_LEN_DATA_AT_EXEC (*length*), данные для этих значений отправляются с помощью **SQLPutData** обычным способом. Следующие аспекты этого процесса задают Специальный комментарий, так как они не очевидны.  
  
-   Когда драйвер возвращает SQL_NEED_DATA, он должен задать в качестве адреса переменной номер строки, для которой требуются данные. Как и в случае с одним значением, приложение не может делать никаких предположений о порядке, в котором драйвер будет запрашивать значения параметров в одном наборе параметров. Если при выполнении параметра данных во время выполнения возникает ошибка, буфер, заданный атрибутом SQL_ATTR_PARAMS_PROCESSED_PTR, задает номер строки, в которой произошла ошибка, состояние строки в массиве состояния строки, заданном атрибутом инструкции SQL_ATTR_PARAM_STATUS_PTR, устанавливается в значение SQL_PARAM_ERROR, а вызов **SQLExecute**, **SQLExecDirect**, **метод SQLParamData**или **SQLPutData** возвращает SQL_ERROR. Содержимое этого буфера не определено, если **SQLExecute**, **SQLExecDirect**или **метод SQLParamData** возвращают SQL_STILL_EXECUTING.  
  
-   Так как драйвер не интерпретирует значение в аргументе *параметервалуептр* параметра **SQLBindParameter** для параметров данных при выполнении, если приложение предоставляет указатель на массив, **метод SQLParamData** не извлекает и не возвращает элемент этого массива в приложение. Вместо этого он возвращает скалярное значение, которое было указано приложением. Это означает, что значение, возвращаемое функцией **метод SQLParamData** , недостаточно для указания параметра, для которого приложению требуется отправка данных. приложению также необходимо учитывать номер текущей строки.  
  
     Если только некоторые элементы массива параметров являются параметрами, выполняемыми при выполнении, приложение должно передать адрес массива в *параметервалуептр* , который содержит элементы для всех параметров. Этот массив интерпретируется как обычно для параметров, не являющихся параметрами выполнения. Для параметров данных, выполняемых при выполнении, значение, которое **метод SQLParamData** предоставляет приложению, которое обычно может использоваться для указания данных, запрашиваемых драйвером в данный момент, всегда является адресом массива.
