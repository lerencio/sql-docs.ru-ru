---
title: Поиск с использованием подстановочных знаков (%)
ms.custom: seo-lt-2019
ms.date: 12/06/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- '%'
- '%_TSQL'
- wildcard
dev_langs:
- TSQL
helpviewer_keywords:
- conditions [SQL Server], wildcards
- '% (wildcard - character(s) to match)'
- matching conditions [SQL Server]
- wildcard characters [SQL Server]
- characters [SQL Server], wildcard
ms.assetid: d4cbc1a9-37e1-4101-97fb-e6ac30c1223e
author: rothja
ms.author: jroth
ms.openlocfilehash: 156ee6ad9860838b1d750f523cd936cbce15e0fb
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85736331"
---
# <a name="percent-character-wildcard---characters-to-match-transact-sql"></a>Символ процента (Cимволы-шаблоны совпадения) (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Совпадает с любой строкой из нуля или более символов. Этот символ-шаблон может быть использован как префикс или суффикс.  
  
## <a name="examples"></a>Примеры  
 Следующий пример возвращает все имена людей в таблице `Person` базы данных `AdventureWorks2012`, которые начинаются с `Dan`.  
  
```  
-- Uses AdventureWorks  
  
SELECT FirstName, LastName  
FROM Person.Person  
WHERE FirstName LIKE 'Dan%';  
GO  
```  
  
## <a name="see-also"></a>См. также:  
 [LIKE (Transact-SQL)](../../t-sql/language-elements/like-transact-sql.md)   
 [Операторы (Transact-SQL)](../../t-sql/language-elements/operators-transact-sql.md)   
 [Выражения (Transact-SQL)](../../t-sql/language-elements/expressions-transact-sql.md)  
 [[ ] (подстановочный знак — символы для сопоставления)](../../t-sql/language-elements/wildcard-character-s-to-match-transact-sql.md)   
  [&#91;^&#93; (подстановочный знак — символы не для сопоставления)](../../t-sql/language-elements/wildcard-character-s-not-to-match-transact-sql.md)     
 [_ (подстановочный знак — совпадение одного символа)](../../t-sql/language-elements/wildcard-match-one-character-transact-sql.md)  
    
  
