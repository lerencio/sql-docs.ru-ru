---
title: Функция Склканцелхандле | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
f1_keywords:
- SQLCancelHandle
helpviewer_keywords:
- SQLCancelHandle function [ODBC]
ms.assetid: 16049b5b-22a7-4640-9897-c25dd0f19d21
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b3f9dcb6ccdef290b937b1317271758dddc0e848
ms.sourcegitcommit: dacd9b6f90e6772a778a3235fb69412662572d02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2020
ms.locfileid: "86279604"
---
# <a name="sqlcancelhandle-function"></a>Функция SQLCancelHandle
**Соответствия**  
 Введенная версия: соответствие стандартам ODBC 3,8: нет  
  
 Ожидается, что большинство драйверов ODBC 3,8 (и более поздних версий) будет реализовывать эту функцию. Если драйвер не работает, вызов **склканцелхандле** с помощью маркера подключения в параметре *Handle* ВОЗВРАТИТ SQL_ERROR с SQLSTATE IM001, а драйвер Message "не поддерживает эту функцию" "вызов **склканцелхандле** с помощью маркера инструкции, так как параметр *Handle* будет сопоставлен с вызовом **SQLCancel** диспетчером драйверов и может быть обработан, если драйвер реализует **SQLCancel**. Приложение может использовать **SQLGetFunctions** , чтобы определить, поддерживает ли драйвер **склканцелхандле**.  
  
 **Сводка**  
 **Склканцелхандле** Отменяет обработку соединения или инструкции. Диспетчер драйверов сопоставляет вызов **склканцелхандле** с вызовом **SQLCancel** , когда *параметром handletype* SQL_HANDLE_STMT.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
  
SQLRETURN SQLCancelHandle(  
      SQLSMALLINT  HandleType,  
      SQLHANDLE    Handle);  
```  
  
## <a name="arguments"></a>Аргументы  
 *HandleType*  
 Входной Тип маркера, на котором кацел обработка. Допустимые значения: SQL_HANDLE_DBC или SQL_HANDLE_STMT.  
  
 *Дескриптор*  
 Входной Маркер, по которому отменяется обработка.  
  
 Если *Handle* не является допустимым маркером типа, указанного параметром *параметром handletype*, **склканцелхандле** возвращает SQL_INVALID_HANDLE.  
  
## <a name="returns"></a>Результаты  
 SQL_SUCCESS, SQL_SUCCESS_WITH_INFO, SQL_ERROR или SQL_INVALID_HANDLE.  
  
## <a name="diagnostics"></a>Диагностика  
 Когда **склканцелхандле** возвращает SQL_ERROR или SQL_SUCCESS_WITH_INFO, связанное значение SQLSTATE может быть получено путем вызова **SQLGetDiagRec** с *параметром handletype* SQL_HANDLE_STMT и *маркером* обработчика инструкции или *параметром handletype* SQL_HANDLE_DBC и *маркером*обработчика соединения.  
  
 В следующей таблице перечислены значения SQLSTATE, обычно возвращаемые функцией **склканцелхандле** , и объясняется каждый из них в контексте этой функции. Нотация "(DM)" предшествует описаниям SQLSTATE, возвращаемым диспетчером драйверов. Код возврата, связанный с каждым значением SQLSTATE, имеет SQL_ERROR, если не указано иное.  
  
|SQLSTATE|Ошибка|Описание|  
|--------------|-----------|-----------------|  
|01000|Общее предупреждение|Информационное сообщение для конкретного драйвера. (Функция возвращает SQL_SUCCESS_WITH_INFO.)|  
|HY000|Общая ошибка|Произошла ошибка, для которой нет определенного SQLSTATE и для которого не определен SQLSTATE для конкретной реализации. Сообщение об ошибке, возвращенное функцией [SQLGetDiagRec](../../../odbc/reference/syntax/sqlgetdiagrec-function.md) в буфере * \* MessageText* , описывает ошибку и ее причину.|  
|HY001|Ошибка выделения памяти|Драйверу не удалось выделить память, необходимую для поддержки выполнения или завершения функции.|  
|HY010|Ошибка последовательности функций|Асинхронно выполняющаяся функция, связанная с инструкцией, была вызвана для одного из дескрипторов инструкций, связанных с *дескриптором*, а для *параметром handletype* было задано значение SQL_HANDLE_DBC. Асинхронная функция все еще выполнялась при вызове **склканцелхандле** .<br /><br /> (DM) аргумент *параметром handletype* был SQL_HANDLE_STMT; в связанном обработчике соединения вызвана асинхронно исполняемая функция; и функция все еще выполнялась при вызове этой функции.<br /><br /> (DM) **SQLExecute**, **SQLExecDirect**или **SQLMoreResults** были вызваны для одного из дескрипторов инструкций, связанных с *дескриптором* , а *параметром handletype* был установлен в SQL_HANDLE_DBC и возвращены SQL_PARAM_DATA_AVAILABLE. Эта функция была вызвана до получения данных для всех потоковых параметров.<br /><br /> **SQLBrowseConnect** был вызван для *коннектионхандле*и вернул SQL_NEED_DATA. Эта функция была вызвана до завершения процесса обзора.|  
|HY013|Ошибка управления памятью|Не удалось обработать вызов функции, так как не удалось получить доступ к базовым объектам памяти, возможно, из-за нехватки памяти.|  
|HY092|Недопустимый идентификатор атрибута или параметра|Для *параметром handletype* задано значение SQL_HANDLE_ENV или SQL_HANDLE_DESC.|  
|HY117|Подключение приостановлено из-за неизвестного состояния транзакции. Допускаются только функции отключения и только для чтения.|(DM) Дополнительные сведения о состоянии SUSPENDED см. в разделе [функция SQLEndTran](../../../odbc/reference/syntax/sqlendtran-function.md).|  
|HYT01|Время ожидания подключения истекло|Время ожидания соединения истекло до ответа источника данных на запрос. Время ожидания соединения задается через **SQLSetConnectAttr**, SQL_ATTR_CONNECTION_TIMEOUT.|  
|IM001|Драйвер не поддерживает эту функцию|(DM) драйвер, связанный с этим *обработчиком* , не поддерживает функцию.|  
  
 Если **склканцелхандле** вызывается с параметром *параметром handletype* , для которого задано значение SQL_HANDLE_STMT, он может вернуть любые значения SQLSTATE, которые могут возвращаться функцией **SQLCancel**.  
  
## <a name="comments"></a>Примечания  
 Эта функция похожа на **SQLCancel** , но в качестве параметра может принимать либо соединение, либо обработчик инструкции, а не только маркер инструкции. Диспетчер драйверов сопоставляет вызов **склканцелхандле** с вызовом **SQLCancel** , когда *параметром handletype* SQL_HANDLE_STMT. Это позволяет приложениям использовать **склканцелхандле** для отмены операций с инструкциями, даже если драйвер не реализует **склканцелхандле**.  
  
 Дополнительные сведения об отмене операции с инструкцией см. в разделе [функция SQLCancel](../../../odbc/reference/syntax/sqlcancel-function.md).  
  
 Если нет выполняющихся операций над *обработчиком* , вызов **склканцелхандле** не оказывает никакого влияния.  
  
 **Склканцелхандле** для маркера подключения может отменить следующие типы обработки:  
  
-   Функция, выполняющаяся асинхронно для соединения.  
  
-   Функция, выполняемая в обработчике соединения в другом потоке.  
  
 При вызове **склканцелхандле** для отмены функции, выполняющейся асинхронно в соединении, записи диагностики, размещенные **склканцелхандле** , добавляются к возвращаемым операцией отмены. Однако **склканцелхандле** не возвращает диагностические записи при отмене функции, выполняющейся в соединении другого потока.  
  
 Использование **склканцелхандле** для отмены **SQLEndTran** может привести к постановке подключения в состояние SUSPENDED. Дополнительные сведения о состоянии SUSPENDED см. в разделе [функция SQLEndTran](../../../odbc/reference/syntax/sqlendtran-function.md).  
  
> [!NOTE]  
>  Сведения об использовании **склканцелхандле** в приложении, которое будет развертываться в операционной системе Windows более ранней, чем Windows 7, см. в разделе [Таблица совместимости](../../../odbc/reference/develop-app/compatibility-matrix.md).  
  
#### <a name="canceling-connection-related-asynchronous-processing"></a>Отмена асинхронной обработки, связанной с подключением  
 Если функция возвращает SQL_STILL_EXECUTING, приложение может вызвать **склканцелхандле** для отмены операции. Если запрос на отмену выполнен успешно, **склканцелхандле** возвращает SQL_SUCCESS. Это не означает, что исходная функция была отменена; Указывает, что запрос отмены обработан. Драйвер и источник данных определяют, когда или если операция отменена. Приложение должно продолжать вызывать исходную функцию, пока не будет SQL_STILL_EXECUTING код возврата. Если исходная функция была отменена, код возврата будет SQL_ERROR и SQLSTATE HY008 (операция отменена). Если исходная функция завершила нормальную обработку (не была отменена), код возврата SQL_SUCCESS или SQL_SUCCESS_WITH_INFO, либо SQL_ERROR и значение SQLSTATE, отличное от HY008 (операция отменена), если исходная функция завершилась ошибкой.  
  
#### <a name="canceling-functions-executing-on-another-thread"></a>Отмена функций, выполняемых в другом потоке  
 В многопоточном приложении Приложение может отменить операцию, выполняемую в другом потоке. Чтобы отменить операцию, приложение вызывает **склканцелхандле** с помощью маркера, используемого функцией, но в другом потоке. Процесс отмены операции определяется драйвером и операционной системой. Код возврата **склканцелхандле** указывает, обрабатывает ли драйвер запрос, возвращая либо SQL_SUCCESS, либо SQL_ERROR (диагностические данные не возвращаются). Если обработка исходной функции отменена, то исходная функция возвращает SQL_ERROR и SQLSTATE HY008 (операция отменена).  
  
 Если функция выполняется при вызове **склканцелхандле** в другом потоке для отмены функции, возможно, что функция будет выполнена и возвращать SQL_SUCCESS до того, как отмена может вступить в силу. Вызов **склканцелхандле** не действует, если операция завершилась до того, как **склканцелхандле** смог отменить операцию.  
  
## <a name="related-functions"></a>Связанные функции  
  
|Сведения о|См.|  
|---------------------------|---------|  
|Отмена функции, выполняющейся асинхронно, в обработчике инструкции, Отмена функции в инструкции, которой требуются данные, или Отмена функции, выполняющейся в операторе другого потока.|[Функция SQLCancel](../../../odbc/reference/syntax/sqlcancel-function.md)|  
  
## <a name="see-also"></a>См. также  
 [Справочник по API ODBC](../../../odbc/reference/syntax/odbc-api-reference.md)   
 [Файлы заголовков ODBC](../../../odbc/reference/install/odbc-header-files.md)   
 [Асинхронное выполнение (метод опроса)](../../../odbc/reference/develop-app/asynchronous-execution-polling-method.md)
