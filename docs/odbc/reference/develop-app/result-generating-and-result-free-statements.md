---
title: Инструкции, создающие результат и без результата | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- result-generating statements [ODBC]
- batches [ODBC], result-generating statements
- batches [ODBC], result-free statements
- SQL statements [ODBC], batches
- result-free statements [ODBC]
ms.assetid: 2f3475d1-3999-4dd8-aba2-a6e1299c95f8
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: fc94aabd7982fba5879519573980db03b1857ef6
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81300094"
---
# <a name="result-generating-and-result-free-statements"></a>Инструкции, возвращающие и не возвращающие результаты
Инструкции SQL можно свободно разделить на следующие пять категорий:  
  
-   **Инструкции создания результирующего набора** Это инструкции SQL, создающие результирующий набор. Например, инструкция **SELECT** .  
  
-   **Счетчик строк — Создание инструкций** Это инструкции SQL, которые создают количество затронутых строк. Например, инструкция **Update** или **Delete** .  
  
-   **Инструкции языка описания данных DDL** Это инструкции SQL, которые изменяют структуру базы данных. Например, **CREATE TABLE** или **DROP INDEX**.  
  
-   **Контекстно-изменяемые инструкции** Это инструкции SQL, которые изменяют контекст базы данных. Например, инструкции **use** и **Set** в SQL Server.  
  
-   **Административные инструкции** Это инструкции SQL, используемые для административных целей в базе данных. Например, **Grant** и **REVOKE**.  
  
 Инструкции SQL в первых двух категориях вместе называются *операторами создания результатов*. Инструкции SQL в последних трех категориях вместе называются *инструкциями без результатов*. ODBC определяет семантику пакетов, включающих только инструкции, создающие результаты. Такая семантика сильно различается и, следовательно, зависит от источника данных. Например, драйвер SQL Server не поддерживает удаление объекта, а затем ссылки или повторное создание того же объекта в том же пакете. Таким образом, термин *пакет* , используемый в этом руководстве, относится только к пакетам инструкций, создающих результаты.
