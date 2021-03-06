---
title: Повторная инициализация подписок — все подписки | Документация Майкрософт
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.reinit.all.f1
helpviewer_keywords:
- Reinitialize Subscription(s) dialog box
ms.assetid: e1122018-9f74-43e3-8489-7eae33ff23d9
author: MashaMSFT
ms.author: mathoma
monikerRange: =azuresqldb-mi-current||>=sql-server-2016||=sqlallproducts-allversions
ms.openlocfilehash: 9da983b0f59625c6bd2404512e99d4f0928bff01
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85767696"
---
# <a name="reinitialize-subscriptions---all-subscriptions"></a>Повторная инициализация подписок — все подписки
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]
  Диалоговое окно **Повторная инициализация подписок** позволяет пометить все подписки публикации для повторной инициализации. Повторная инициализация заключается в том, что к каждому подписчику применяется моментальный снимок; эта задача выполняется агентом распространителя для подписок на публикации транзакций и агентом слияния для подписок на публикации слиянием.  
  
## <a name="options"></a>Параметры  
 **Использовать текущий моментальный снимок**  
 Выберите, чтобы при следующем запуске агента распространителя или агента слияния для данной подписки применить текущий моментальный снимок к каждому из подписчиков. Если допустимый моментальный снимок отсутствует, этот параметр выбрать нельзя.  
  
 **Использовать новый моментальный снимок**  
 Выберите, чтобы выполнить повторную инициализацию всех подписок с новым моментальным снимком. Этот моментальный снимок можно применять к каждому подписчику только после того, как он был сформирован агентом моментальных снимков. Если запуск агента моментальных снимков производится по расписанию, подписки не будут повторно инициализированы до его следующего запуска.  
  
 Выберите **Создать новый моментальный снимок** для немедленного запуска агента моментальных снимков.  
  
 **Передать несинхронизированные изменения перед повторной инициализацией**  
 Только репликация слиянием. Выберите, чтобы передать все ожидающие обработки изменения из баз данных подписки, прежде чем данные на подписчиках будут перезаписаны моментальным снимком.  
  
 Если добавить, удалить или изменить параметризованный фильтр, ожидающие обработки изменения подписчика нельзя будет передать издателю во время повторной инициализации. Если нужно передать изменения, ожидающие обработки, то перед изменением фильтра необходимо синхронизировать все подписки.  
  
 **Пометить для повторной инициализации**  
 Выберите, чтобы пометить каждую из подписок для повторной инициализации. После того как будет доступен моментальный снимок, при следующем запуске для подписки агента распространителя или агента слияния он применяется к подписчику.  
  
## <a name="see-also"></a>См. также:  
 [Повторная инициализация подписок](../../relational-databases/replication/reinitialize-subscriptions.md)  
  
  
