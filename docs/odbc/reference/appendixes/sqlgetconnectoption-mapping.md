---
title: Сопоставление SQLGetConnectOption | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- mapping deprecated functions [ODBC], SQLGetConnectOption
- SQLGetConnectOption function [ODBC], mapping
ms.assetid: e3792fe4-a955-473a-a297-c1b2403660c4
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 8d2905bd6793d032e485183c8f553cef2cdefda3
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81302005"
---
# <a name="sqlgetconnectoption-mapping"></a>Сопоставление SQLGetConnectOption
Когда приложение вызывает **SQLGetConnectOption** через драйвер ODBC *3. x* , вызов метода  
  
```  
SQLGetConnectOption(hdbc, fOption, pvParam)   
```  
  
 сопоставляется следующим образом:  
  
-   Если *параметром fOption* указывает параметр соединения, определяемый ODBC, который возвращает строку, диспетчер драйверов вызывает метод  
  
    ```  
    SQLGetConnectAttr(ConnectionHandle, Attribute, ValuePtr, BufferLength, NULL)  
    ```  
  
-   Если *параметром fOption* указывает параметр соединения, определяемый ODBC, который возвращает 32-разрядное целое значение, диспетчер драйверов вызывает  
  
    ```  
    SQLGetConnectAttr(ConnectionHandle, Attribute, ValuePtr, 0, NULL)  
    ```  
  
-   Если *параметром fOption* указывает параметр инструкции, определяемый драйвером, диспетчер драйверов вызывает  
  
    ```  
    SQLGetConnectAttr(ConnectionHandle, Attribute, ValuePtr, BufferLength, NULL)  
    ```  
  
 В предыдущих трех случаях аргументу *коннектионхандле* присваивается значение в *хдбк*, аргументу *атрибута* присваивается значение в *параметром fOption*, а аргументу *ValuePtr* присваивается то же значение, что и *пвпарам*.  
  
 Для параметров соединения, определенных ODBC, диспетчер драйверов устанавливает аргумент *BufferLength* в вызове **SQLGetConnectAttr** до предопределенной максимальной длины (SQL_MAX_OPTION_STRING_LENGTH); для параметра соединения, не предназначенного для строки, *BufferLength* имеет значение 0.  
  
 Для драйвера ODBC *3. x* диспетчер драйверов больше не проверяет, находится ли *параметр* между SQL_CONN_OPT_MIN и SQL_CONN_OPT_MAX или больше SQL_CONNECT_OPT_DRVR_START. Драйвер должен проверить допустимость значений параметров.
