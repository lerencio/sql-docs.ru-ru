---
title: Свойство "команда повторной синхронизации" — Dynamic (ADO) | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- Resync Command property [ADO]
ms.assetid: 4e2bb601-0fe8-4d61-b00e-38341d85a6bb
author: rothja
ms.author: jroth
ms.openlocfilehash: 916afef294a76e62702dbbd7cc413a0540484f62
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82756481"
---
# <a name="resync-command-property-dynamic-ado"></a>Свойство Resync Command (динамическое) (ADO)
Указывает указанную пользователем строку команды, которая выдается методом повторной [синхронизации](../../../ado/reference/ado-api/resync-method.md) для обновления данных в таблице, указанной в динамическом свойстве [уникальной таблицы](../../../ado/reference/ado-api/unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) .  
  
## <a name="settings-and-return-values"></a>Параметры и возвращаемые значения  
 Задает или возвращает **строковое** значение, представляющее собой командную строку.  
  
## <a name="remarks"></a>Remarks  
 Объект [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) является результатом операции JOIN, выполняемой над несколькими базовыми таблицами. Затронутые строки зависят от параметра *аффектрекордс* метода [Resync](../../../ado/reference/ado-api/resync-method.md) . Стандартный метод повторной **синхронизации** выполняется, если не заданы свойства " [уникальная таблица](../../../ado/reference/ado-api/unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) " и " **Повторная синхронизация** ".  
  
 Командная строка свойства Command повторной **синхронизации** — это параметризованная команда или хранимая процедура, которая однозначно определяет обновляемую строку и возвращает одну строку, содержащую то же число и порядок столбцов, что и обновляемая строка. Командная строка содержит параметр для каждого первичного ключевого столбца в **уникальной таблице**; в противном случае возвращается ошибка времени выполнения. Параметры автоматически заполняются значениями первичного ключа из обновляемой строки.  
  
 Ниже приведены два примера, основанные на SQL:  
  
 1 \) **набор записей** определяется командой:  
  
```  
SELECT * FROM Customers JOIN Orders ON   
   Customers.CustomerID = Orders.CustomerID  
   WHERE city = 'Seattle'  
   ORDER BY CustomerID  
```  
  
 Для свойства "команда повторной **синхронизации** " задано значение:  
  
```  
"SELECT * FROM   
   (SELECT * FROM Customers JOIN Orders   
   ON Customers.CustomerID = Orders.CustomerID  
   city = 'Seattle' ORDER BY CustomerID)  
WHERE Orders.OrderID = ?"  
```  
  
 **Уникальная таблица** — это *Orders* , а ее первичный ключ — *OrderID*. Подзапрос выборки предоставляет простой способ программно гарантировать, что то же количество и порядок столбцов возвращаются в виде исходной команды.  
  
 2 \) **набор записей** определяется хранимой процедурой.  
  
```  
CREATE PROC Custorders @CustomerID char(5) AS   
SELECT * FROM Customers JOIN Orders ON   
Customers.CustomerID = Orders.CustomerID   
WHERE Customers.CustomerID = @CustomerID  
```  
  
 Метод **Resync** должен выполнить следующую хранимую процедуру:  
  
```  
CREATE PROC CustordersResync @ordid int AS   
SELECT * FROM Customers JOIN Orders ON   
Customers.CustomerID = Orders.CustomerID  
WHERE Orders.ordid  = @ordid  
```  
  
 Для свойства "команда повторной **синхронизации** " задано значение:  
  
```  
"{call CustordersResync (?)}"  
```  
  
 Опять же, **уникальная таблица** — это *Orders* , а ее первичный ключ — *OrderID*.  
  
 **Команда** повторной синхронизации — это динамическое свойство, добавленное к коллекции [свойств](../../../ado/reference/ado-api/properties-collection-ado.md) объекта **Recordset** , если свойство [CursorLocation](../../../ado/reference/ado-api/cursorlocation-property-ado.md) имеет значение **адусеклиент**.  
  
## <a name="applies-to"></a>Применяется к  
 [Объект Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)
