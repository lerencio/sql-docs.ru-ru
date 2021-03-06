---
title: Настройка параметров трассировки | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio Analyzer tracing [ODBC]
- ODBC data source administrator [ODBC], tracing options
- tracing options [ODBC], ODBC data source administrator
ms.assetid: 44404a79-b716-4bc1-9ffb-70cd8239d237
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 21bee5d903459423a134389e62db844f5f63c9c1
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81307204"
---
# <a name="setting-tracing-options"></a>Настройка параметров трассировки
Вкладка **Трассировка** диалогового окна **Администратор источников данных ODBC** позволяет настроить способ трассировки вызовов функций ODBC.  
  
## <a name="how-tracing-works"></a>Принцип работы трассировки  
 При запуске трассировки на вкладке « **Трассировка** » диспетчер драйверов регистрирует все вызовы функций ODBC для всех последующим запуском приложений. Вызовы функций ODBC из приложений, выполняемых до начала трассировки, не регистрируются. Вызовы функций ODBC записываются в указанный файл журнала.  
  
 Трассировка останавливается только после нажатия кнопки **остановить трассировку**. Помните, что хотя трассировка включена, файл журнала продолжит расти, и это влияет на производительность всех приложений ODBC.  
  
 Дополнительные сведения о трассировке см. в разделе [Трассировка](../../odbc/reference/develop-app/tracing.md).  
  
### <a name="changes-in-odbc-tracing"></a>Изменения в трассировке ODBC  
 До MDAC 2,7 с пакетом обновления 2 (SP2) трассировка ODBC была разрешена только на уровне компьютера, при котором Трассировка захватывает сведения обо всех приложениях ODBC, работающих с любыми удостоверениями. Это включало трассировку действий, связанных с ODBC, которые могут возникнуть для процессов, созданных или выполняемых от имени других локальных учетных записей пользователей и встроенных субъектов безопасности, таких как локальная служба и сетевая служба.  
  
 По умолчанию трассировка ODBC теперь использует режим "на пользователя". Однако если вы являетесь локальным администратором, вы по-прежнему можете включить трассировку на уровне компьютера с помощью администратора источников данных ODBC.  
  
 Чтобы настроить режим трассировки ODBC, выполните следующие действия.  
  
1.  При необходимости войдите в систему, используя учетную запись с членством в группе локальных администраторов.  
  
2.  В меню Администрирование откройте Администратор источников данных ODBC.  
  
3.  Перейдите на вкладку **Трассировка** .  
  
4.  Настройте режим трассировки, используя **трассировку на уровне компьютера для всех удостоверений пользователей** :  
  
5.  Чтобы включить трассировку на уровне компьютера, установите флажок.  
  
6.  Чтобы вернуться к трассировке на уровне пользователя, снимите флажок.  
  
7.  Нажмите кнопку **Применить**.  
  
> [!NOTE]  
>  Если трассировка уже запущена в одном режиме, необходимо прерывать трассировку и переключаться в другой режим, чтобы успешно изменить режим.  
  
> [!IMPORTANT]  
>  Трассировка на уровне компьютера должна быть включена только при необходимости; в противном случае она должна быть отключена.  
  
## <a name="visual-studio-analyzer-tracing"></a>Трассировка анализатор Visual Studio  
  
> [!IMPORTANT]  
>  Поддержка анализатор Visual Studio была удалена начиная с Windows 8 (анализатор Visual Studio была включена только в более ранних версиях Visual Studio.) Для альтернативного механизма устранения неполадок используйте трассировку ТЕНДЕРа.  
  
 Трассировка анализатора® Visual Studio предоставляет сведения о производительности и отладке уровня ODBC. Все исходящие события будут срабатывать в интерфейсе верхнего уровня, чтобы обеспечить максимально точную картину в отношении времени, затраченного на компоненты ODBC. Для трассировки анализатор Visual Studio требуется, чтобы источник событий регистрировался при настройке источника. Дополнительные сведения об этом типе трассировки см. в документации по Visual Studio.
