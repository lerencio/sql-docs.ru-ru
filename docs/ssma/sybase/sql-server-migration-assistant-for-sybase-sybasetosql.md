---
title: Помощник по миграции SQL Server для Sybase (SybaseToSQL) | Документация Майкрософт
description: Узнайте о SSMA для Sybase и выполните пошаговые инструкции по переносу баз данных ASE в SQL Server или базу данных SQL Azure.
ms.custom: ''
ms.date: 10/10/2019
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 59e63eac-8a7e-4d54-be1c-0633a9bf510d
author: Jtoland
ms.author: Jtoland
manager: murato
ms.openlocfilehash: 269fa36b578b7b13d12d5b6fd9645e84c7c39244
ms.sourcegitcommit: 59cda5a481cfdb4268b2744edc341172e53dede4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84293993"
---
# <a name="sql-server-migration-assistant-for-sybase-sybasetosql"></a>Помощник по миграции SQL Server для Sybase (SybaseToSQL)

[!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Помощник по миграции (SSMA) для адаптивного серверного предприятия Sybase (ASE) — это средство для переноса баз данных ASE в [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2012, [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2014, [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2016, [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2017 в Windows и Linux, [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2019 в Windows и Linux или [!INCLUDE[msCoName](../../includes/msconame_md.md)] база данных SQL Azure. SSMA для Sybase преобразует объекты базы данных ASE в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] объекты базы данных, создает эти объекты в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или базе данных SQL Azure, а затем переносит данные из ASE в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или базу данных SQL Azure.
  
В этой документации описывается SSMA для Sybase и приводятся пошаговые инструкции по переносу баз данных ASE в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базу данных SQL Azure и сведения о проблемах, которые могут возникнуть после миграции. Дополнительные сведения см. в следующих статьях.  
  
## <a name="contents"></a>Содержимое  
  
|Section|Описание|
|-----------|---------------|
|[Новые возможности в SSMA для Sybase &#40;SybaseToSQL&#41;](../../ssma/sybase/what-s-new-in-ssma-for-sybase-sybasetosql.md)|Перечисляет изменения в выпусках SSMA.|  
|[Установка SSMA для Sybase &#40;SybaseToSQL&#41;](../../ssma/sybase/installing-ssma-for-sybase-sybasetosql.md)|Содержит статьи, содержащие предварительные требования и инструкции по установке SSMA для клиента Sybase и необходимых компонентов на компьютере, на котором выполняется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] экземпляр.|  
|[Начало работы с SSMA для Sybase &#40;SybaseToSQL&#41;](../../ssma/sybase/getting-started-with-ssma-for-sybase-sybasetosql.md)|Представляет пользовательский интерфейс, проекты и параметры конфигурации.|  
|[Миграция баз данных Sybase ASE в SQL Server Azure SQL DB &#40;SybaseToSQL&#41;](../../ssma/sybase/migrating-sybase-ase-databases-to-sql-server-azure-sql-db-sybasetosql.md)|Содержит общие сведения о процессе преобразования и подробные сведения о каждом шаге процесса.|  
|[Справочник по пользовательскому интерфейсу &#40;SybaseToSQL&#41;](../../ssma/sybase/user-interface-reference-sybasetosql.md)|Содержит документацию для диалоговых окон SSMA для Sybase.|  
|[Работа с консолью SSMA для Sybase](working-with-ssma-for-sybase-console-sybasetosql.md)|Содержит документацию по консольному приложению SSMA.|  
|[Получение помощи по SSMA для Sybase](https://go.microsoft.com/fwlink/?LinkID=708538&clcid=0x409)|Содержит сведения о получении дополнительной помощи.|  
