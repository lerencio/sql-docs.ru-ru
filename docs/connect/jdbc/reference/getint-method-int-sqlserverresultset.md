---
title: Метод getInt (int) (SQLServerResultSet) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.getInt (int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: c465ff91-ab96-41de-8917-96c4974c2624
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: d781afd23abb13e398ee1f2f99c1428066b6ca60
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80921470"
---
# <a name="getint-method-int-sqlserverresultset"></a>Метод getInt (int) (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Получает значение индекса заданного столбца в текущей строке этого объекта [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) в виде значения типа **int** на языке программирования Java.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
public int getInt(int columnIndex)  
```  
  
#### <a name="parameters"></a>Параметры  
 *columnIndex*  
  
 Значение типа **int**, указывающее индекс столбца.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение **int**.  
  
## <a name="exceptions"></a>Исключения  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Этот метод getInt определен с помощью метода getInt в интерфейсе java.sql.ResultSet.  
  
 Этот метод поддерживается только для типов данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], таких как int, smallint, tinyint и bit, которые могут безопасно возвращать целочисленное значение. Использование этого метода при работе со столбцами других типов данных приведет к возникновению исключения.  
  
## <a name="see-also"></a>См. также:  
 [Метод getInt (SQLServerResultSet)](../../../connect/jdbc/reference/getint-method-sqlserverresultset.md)   
 [Элементы SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Класс SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
