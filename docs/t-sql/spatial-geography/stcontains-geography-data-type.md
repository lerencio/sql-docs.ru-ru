---
title: STContains (тип данных geography) | Документы Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- STContains method (geography)
ms.assetid: b10e8f0a-2926-449a-82ea-be42543420ca
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 0c1b1aa4526479675ec6153ad34b3a1e98671ade
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86554743"
---
# <a name="stcontains--geography-data-type"></a>STContains (тип данных geography)
[!INCLUDE [SQL Server Azure SQL Database ](../../includes/applies-to-version/sql-asdb.md)]

  Указывает, содержит ли пространство вызывающего экземпляра **geography** экземпляр **geography**, переданный в метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
.STContains ( other_geography )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Аргументы
 *other_geography*  
 Другой экземпляр **geography** для сравнения с экземпляром, для которого вызван метод `STContains()`.  
  
## <a name="return-types"></a>Типы возвращаемых данных  
 Тип возвращаемых данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **bit**  
  
 Тип возвращаемых данных CLR: **SqlBoolean**  
  
## <a name="remarks"></a>Remarks  
 Возвращает значение 1, если пространство вызывающего экземпляра **geography** содержит экземпляр **geography**, переданный в метод. В противном случае возвращает значение 0. Возвращает **null**, если идентификаторы пространственных ссылок (SRID) двух экземпляров **geography** не совпадают.  
  
## <a name="examples"></a>Примеры  
 В следующем примере используется метод `STContains()`, чтобы проверить два экземпляра `geography` и выяснить, заключается ли второй экземпляр внутри первого.  
  
```  
DECLARE @g geography;  
DECLARE @h geography;  
SET @g = geography::Parse('CURVEPOLYGON (COMPOUNDCURVE (CIRCULARSTRING (-122.200928 47.454094, -122.810669 47.00648, -122.942505 46.687131, -121.14624 45.786679, -119.119263 46.183634), (-119.119263 46.183634, -119.273071 47.107523, -120.640869 47.569114, -122.200928 47.454094)))');  
SET @h = geography::Parse('POINT(-121.703796 46.893985)');  
```  
  
 `SELECT @g.STContains(@h);`  
  
  
