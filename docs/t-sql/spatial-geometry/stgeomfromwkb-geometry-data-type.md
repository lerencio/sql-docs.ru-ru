---
title: STGeomFromWKB (тип данных geometry) | Документы Майкрософт
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- STGeomFromWKB (geometry Data Type)
- STGeomFromWKB_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STGeomFromWKB (geometry Data Type)
ms.assetid: 6546ddb0-4a5f-46e5-ba04-8007486c95ec
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 898b3a613f96de95074547f66962df22033827f8
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86555579"
---
# <a name="stgeomfromwkb-geometry-data-type"></a>STGeomFromWKB (тип данных geometry)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

Возвращает экземпляр **geometry** из WKB-представления открытого геопространственного консорциума (OGC).
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
STGeomFromWKB ( 'WKB_geometry' , SRID )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Аргументы
 *WKB_geometry*  
 WKB-представление возвращаемого экземпляра **geometry**. *WKB_geometry* — это выражение типа **varbinary(max)** .  
  
 *SRID*  
 Выражение типа **int**, представляющее идентификатор пространственной ссылки (SRID) возвращаемого экземпляра **geometry**.  
  
## <a name="return-types"></a>Типы возвращаемых данных  
 Тип возвращаемых данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **geometry**  
  
 Тип возвращаемых данных CLR: **SqlGeometry**  
  
## <a name="remarks"></a>Remarks  
 Тип OGC экземпляра **geometry**, возвращаемый методом `STGeomFromText()`, получает значение в зависимости от соответствующих входных данных WKB.  
  
 Этот метод вызывает исключение **FormatException**, если входные данные представлены в неверном формате.  
  
## <a name="examples"></a>Примеры  
 В приведенном ниже примере используется метод `STGeomFromWKB()`, чтобы создать экземпляр **geometry**.  
  
```  
DECLARE @g geometry;   
SET @g = geometry::STGeomFromWKB(0x010200000003000000000000000000594000000000000059400000000000003440000000000080664000000000008066400000000000806640, 0);  
SELECT @g.STAsText();  
```  
  
## <a name="see-also"></a>См. также:  
 [Статические геометрические методы OGC](../../t-sql/spatial-geometry/ogc-static-geometry-methods.md)  
  
  

