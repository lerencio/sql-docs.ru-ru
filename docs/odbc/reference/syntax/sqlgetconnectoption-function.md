---
title: Функция SQLGetConnectOption | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLGetConnectOption
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLGetConnectOption
helpviewer_keywords:
- SQLGetConnectOption function [ODBC]
ms.assetid: 59cde899-7957-4b5e-8677-f34d3b859bfd
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 94a29637365862990ea067f663023fae04a7af3e
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81285574"
---
# <a name="sqlgetconnectoption-function"></a>Функция SQLGetConnectOption
**Соответствия**  
 Введенная версия: соответствие стандартам ODBC 1,0: не рекомендуется  
  
 **Сводка**  
 В ODBC *3. x*функция ODBC *2. x* **SQLGetConnectOption** была заменена на **SQLGetConnectAttr**. Дополнительные сведения см. в разделе [SQLGetConnectAttr](../../../odbc/reference/syntax/sqlgetconnectattr-function.md).  
  
> [!NOTE]
>  Дополнительные сведения о том, как диспетчер драйверов сопоставляет эту функцию, когда приложение ODBC *2. x* работает с драйвером ODBC *3. x* , см. в разделе [сопоставление устаревших функций](../../../odbc/reference/appendixes/mapping-deprecated-functions.md) в приложении G: рекомендации по драйверу для обеспечения обратной совместимости.  
> 
> [!NOTE]
>  Атрибут SQL_ASYNC_DBC_FUNCTION_ENABLE, введенный в ODBC 3,8, не поддерживается **SQLGetConnectOption**. Приложения, использующие асинхронную операцию с маркером соединения, должны использовать **SQLGetConnectAttr**.  
  
## <a name="see-also"></a>См. также:  
 [Справочник по API ODBC](../../../odbc/reference/syntax/odbc-api-reference.md)   
 [Файлы заголовков ODBC](../../../odbc/reference/install/odbc-header-files.md)
