---
title: Свойство SQLState | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Error::GetSQLState
- Error::SQLState
- Error::get_SQLState
helpviewer_keywords:
- SQLState property
ms.assetid: f9e25967-54b0-444d-af2a-0d2c75365d3e
author: rothja
ms.author: jroth
ms.openlocfilehash: 9b40c35730b02352f1e8667941aa4c220a7ad4df
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82759770"
---
# <a name="sqlstate-property"></a>Свойство SQLState
Указывает состояние SQL для данного объекта [ошибки](../../../ado/reference/ado-api/error-object.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает **строковое** значение из пяти символов, следующее за стандартом ANSI SQL, и указывает код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Используйте свойство **SQLSTATE** для чтения кода ошибки из пяти символов, возвращаемого поставщиком при возникновении ошибки во время обработки инструкции SQL. Например, при использовании поставщика Microsoft OLE DB для ODBC с базой данных Microsoft SQL Server коды ошибок состояния SQL исходят из ODBC, основываясь на ошибках ODBC или об ошибках, происходящих в Microsoft SQL Server, а затем сопоставленных ошибкам ODBC. Эти коды ошибок описаны в стандарте ANSI SQL, но могут быть реализованы по-разному в разных источниках данных.  
  
## <a name="applies-to"></a>Применяется к  
 [Объект Error](../../../ado/reference/ado-api/error-object.md)  
  
## <a name="see-also"></a>См. также  
 [Примеры свойств Description, HelpContext, HelpFile, NativeError, Number, Source и SQLState (Visual Basic)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [Примеры свойств Description, HelpContext, HelpFile, NativeError, Number, Source и SQLState (Visual c++)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   
