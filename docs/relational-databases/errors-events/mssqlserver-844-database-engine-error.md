---
title: MSSQLSERVER_844 | Документация Майкрософт
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 844 (Database Engine error)
ms.assetid: 2060c886-1226-4066-bc0c-de90a1cfb82b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bdc05bbc2cf4db3875149ed35ac82dd922800484
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85767814"
---
# <a name="mssqlserver_844"></a>MSSQLSERVER_844
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Сведения  
  
| attribute | Значение |  
| :-------- | :---- |  
|Название продукта|SQL Server|  
|Идентификатор события|844|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|BUFLATCH_TIMEOUT_CONTINUE|  
|Текст сообщения|Истекло время ожидания кратковременной блокировки буфера — тип %d, базовая точка %p, страница %d:%d, stat %#x, идентификатор базы данных: %d, идентификатор единицы распределения: %I64d%ls, задача 0x%p: %d, время ожидания %d, флаги 0x%I64x, задача-владелец 0x%p.  Продолжение ожидания.|  
  
## <a name="explanation"></a>Объяснение  
Процесс ожидает получения кратковременной блокировки. Эта проблема может быть вызвана слишком продолжительной операцией ввода-вывода. Как правило, этот тип ошибки возникает в результате блокирования системных процессов другими задачами. В некоторых случаях эта ошибка может возникать в результате сбоя оборудования.  
  
## <a name="user-action"></a>Действие пользователя  
Для предотвращения этой ошибки попробуйте предпринять следующее.  
  
-   Снизьте рабочую нагрузку.  
  
-   В журнале ошибок или журнале событий проверьте соответствующие сбои операций ввода-вывода. Сбои операций ввода-вывода обычно указывают на неправильную работу диска.  
  
-   В журнале ошибок проверьте наличие невыполненных задач и других критических ошибок.  
  
-   Если критические ошибки встречаются часто, устраните их причину.  
  
Если ошибка продолжает возникать, обратитесь в службу поддержки пользователей корпорации Майкрософт.  
  
