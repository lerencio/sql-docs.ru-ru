---
title: Функция SQLDisconnect | Документация Майкрософт
ms.custom: ''
ms.date: 07/18/2019
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLDisconnect
apilocation:
- sqlsrv32.dll
- odbc32.dll
apitype: dllExport
f1_keywords:
- SQLDisconnect
helpviewer_keywords:
- SQLDisconnect function [ODBC]
ms.assetid: 9e84a58e-db48-4821-a0cd-5c711fcbe36b
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: a5ea73919fbe90719d881fb43108ab1934933708
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81301154"
---
# <a name="sqldisconnect-function"></a>Функция SQLDisconnect
**Соответствия**  
 Представленная версия: соответствие стандартам ODBC 1,0: ISO 92  
  
 **Сводка**  
 **SQLDisconnect** закрывает подключение, связанное с конкретным маркером подключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
  
SQLRETURN SQLDisconnect(  
     SQLHDBC     ConnectionHandle);  
```  
  
## <a name="arguments"></a>Аргументы  
 *коннектионхандле*  
 [Input] Дескриптор подключения  
  
## <a name="returns"></a>Результаты  
 SQL_SUCCESS, SQL_SUCCESS_WITH_INFO, SQL_ERROR, SQL_INVALID_HANDLE или SQL_STILL_EXECUTING.  
  
## <a name="diagnostics"></a>Диагностика  
 Когда **SQLDisconnect** возвращает SQL_ERROR или SQL_SUCCESS_WITH_INFO, связанное значение SQLSTATE может быть получено путем вызова **SQLGetDiagRec** с *параметром handletype* SQL_HANDLE_DBC и *маркером* *коннектионхандле*. В следующей таблице перечислены значения SQLSTATE, обычно возвращаемые функцией **SQLDisconnect** , и объясняется каждый из них в контексте этой функции. Нотация "(DM)" предшествует описаниям SQLSTATE, возвращаемым диспетчером драйверов. Код возврата, связанный с каждым значением SQLSTATE, имеет SQL_ERROR, если не указано иное.  
  
|SQLSTATE|Error|Описание|  
|--------------|-----------|-----------------|  
|01000|Общее предупреждение|Информационное сообщение для конкретного драйвера. (Функция возвращает SQL_SUCCESS_WITH_INFO.)|  
|01002|Ошибка отключения|Во время отключения произошла ошибка. Однако отключение прошло удачно. (Функция возвращает SQL_SUCCESS_WITH_INFO.)|  
|08003|Соединение не открыто|(DM) подключение, указанное в аргументе *коннектионхандле* , не было открыто.|  
|25000|Недопустимое состояние транзакции|В процессе соединения, указанного аргументом *коннектионхандле*, произошла транзакция. Транзакция остается активной.|  
|HY000|Общая ошибка|Произошла ошибка, для которой нет определенного SQLSTATE и для которого не определен SQLSTATE для конкретной реализации. Сообщение об ошибке, возвращаемое функцией **SQLGetDiagRec** в буфере * \*MessageText* , описывает ошибку и ее причину.|  
|HY001|Ошибка выделения памяти|Драйверу не удалось выделить память, необходимую для поддержки выполнения или завершения функции.|  
|HY008|Operation canceled|Асинхронная обработка включена для *коннектионхандле*. Функция была вызвана, и перед ней завершил выполнение [функции склканцелхандле](../../../odbc/reference/syntax/sqlcancelhandle-function.md) для *коннектионхандле*. Затем функция была вызвана в *коннектионхандле*.<br /><br /> Функция была вызвана, и до завершения выполнения **склканцелхандле** был вызван в *коннектионхандле* из другого потока многопоточного приложения.|  
|HY010|Ошибка последовательности функций|(DM) вызывается асинхронно исполняемая функция для *статеменсандле* , связанной с *коннектионхандле* , и все еще выполнялась при вызове **SQLDisconnect** .<br /><br /> (DM) вызывается асинхронно исполняемая функция (не эта одна) для *коннектионхандле* и все еще выполнялась при вызове этой функции.<br /><br /> (DM) **SQLExecute**, **SQLExecDirect**, **SQLBulkOperations**или **SQLSetPos** были вызваны для *статеменсандле* , связанного с *коннектионхандле* , и возвращены SQL_NEED_DATA. Эта функция была вызвана перед отправкой данных для всех параметров или столбцов данных, выполняемых во время выполнения.|  
|HY013|Ошибка управления памятью|Не удалось обработать вызов функции, так как не удалось получить доступ к базовым объектам памяти, возможно, из-за нехватки памяти.|  
|HY117|Подключение приостановлено из-за неизвестного состояния транзакции. Допускаются только функции отключения и только для чтения.|(DM) Дополнительные сведения о состоянии SUSPENDED см. в разделе [функция SQLEndTran](../../../odbc/reference/syntax/sqlendtran-function.md).|  
|HYT01|Время ожидания подключения истекло|Время ожидания соединения истекло до ответа источника данных на запрос, и соединение все еще активно. Время ожидания соединения задается через **SQLSetConnectAttr**, SQL_ATTR_CONNECTION_TIMEOUT.|  
|IM001|Драйвер не поддерживает эту функцию|(DM) драйвер, связанный с *коннектионхандле* , не поддерживает функцию.|  
|IM017|Опрос отключен в режиме асинхронного уведомления|При использовании модели уведомления опрос отключен.|  
|IM018|**Склкомплетеасинк** не был вызван для завершения предыдущей асинхронной операции с этим обработчиком.|Если предыдущий вызов функции в обработчике возвращает SQL_STILL_EXECUTING и если включен режим уведомления, то для обработки после обработки и завершения операции необходимо вызвать **склкомплетеасинк** .|  
  
## <a name="comments"></a>Комментарии  
 Если приложение вызывает **SQLDisconnect** после того, как **SQLBrowseConnect** возвращает SQL_NEED_DATA и перед возвратом другого кода возврата, драйвер отменяет процесс обзора соединения и возвращает соединение в неподключенное состояние.  
  
 Если приложение вызывает **SQLDisconnect** при наличии незавершенной транзакции, связанной с обработчиком соединения, драйвер ВОЗВРАЩАЕТ значение SQLSTATE 25000 (недопустимое состояние транзакции), указывающее, что транзакция не изменена и соединение открыто. Незавершенная транзакция — это одна из транзакций, которая не была зафиксирована или отменена с помощью **SQLEndTran**.  
  
 Если приложение вызывает **SQLDisconnect** до того, как оно освободило все инструкции, связанные с соединением, драйвер после успешного отключения от источника данных освобождает эти инструкции и все дескрипторы, которые были явно выделены в соединении. Однако если одна или несколько инструкций, связанных с соединением, по-прежнему выполняются асинхронно, **SQLDisconnect** возвращает SQL_ERROR со значением SQLState, HY010 (ошибка последовательности функций). Кроме того, **SQLDisconnect** будет освобождать все связанные инструкции и дескрипторы, которые были явно выделены для соединения, если соединение находится в приостановленном состоянии или если **SQLDisconnect** был успешно отменен **склканцелхандле**.  
  
 Сведения о том, как приложение использует **SQLDisconnect**, см. в разделе [Отключение от источника данных или драйвера](../../../odbc/reference/develop-app/disconnecting-from-a-data-source-or-driver.md).  
  
## <a name="disconnecting-from-a-pooled-connection"></a>Отключение от подключения в составе пула  
 Если для общей среды включена поддержка пулов соединений и приложение вызывает **SQLDisconnect** для подключения в этой среде, подключение возвращается в пул соединений и по-прежнему доступно для других компонентов, использующих ту же общую среду.  
  
## <a name="code-example"></a>Пример кода  
 См. [Пример программы ODBC](../../../odbc/reference/sample-odbc-program.md), [функция SQLBrowseConnect](../../../odbc/reference/syntax/sqlbrowseconnect-function.md)и [Функция SQLConnect](../../../odbc/reference/syntax/sqlconnect-function.md).  
  
## <a name="related-functions"></a>Связанные функции  
  
|Сведения о|См.|  
|---------------------------|---------|  
|Выделение маркера|[Функция SQLAllocHandle](../../../odbc/reference/syntax/sqlallochandle-function.md)|  
|Подключение к источнику данных|[Функция SQLConnect](../../../odbc/reference/syntax/sqlconnect-function.md)|  
|Соединение с источником данных с помощью строки подключения или диалогового окна|[Функция SQLDriverConnect](../../../odbc/reference/syntax/sqldriverconnect-function.md)|  
|Выполнение операции фиксации или отката|[Функция SQLEndTran](../../../odbc/reference/syntax/sqlendtran-function.md)|  
|Освобождение маркера подключения|[Функция SQLFreeConnect](../../../odbc/reference/syntax/sqlfreeconnect-function.md)|  
  
## <a name="see-also"></a>См. также:  
 [Справочник по API ODBC](../../../odbc/reference/syntax/odbc-api-reference.md)   
 [Файлы заголовков ODBC](../../../odbc/reference/install/odbc-header-files.md)
