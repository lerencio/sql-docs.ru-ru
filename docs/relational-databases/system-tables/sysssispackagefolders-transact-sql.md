---
title: sysssispackagefolders (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysdtspackagefolders90
- sysdtspackagefolders90_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysssispackagefolders system table
ms.assetid: ddc4833f-27bf-4610-b739-d257961d17ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c525b1b457c2bc9f505a83cc89a08a57c27e6279
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85881282"
---
# <a name="sysssispackagefolders-transact-sql"></a>sysssispackagefolders (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Содержит по одной строке для каждой логической папки в иерархии папок, в которой [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] используется. Эти папки перечислены в обозревателе объектов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] при подключении к службам [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]. В папке перечисляются пакеты, сохраненные в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или в файловой системе.  
  
 Столбец **parentfolderid** описывает иерархию папок. Папка в верхней части иерархии папок содержит значение NULL в **parentfolderid**.  
  
 Столбец **имя_папки** содержит имена папок, которые отображаются в обозревателе объектов.  
  
 Эта таблица хранится в базе данных **msdb** .  

  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**FolderId**|**uniqueidentifier**|Идентификатор GUID папки.|  
|**parentfolderid**|**uniqueidentifier**|Идентификатор GUID родительской папки.|  
|**имя_папки**|**sysname**|Имя папки. Это имя появляется в иерархии папок в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].|  
  
  
