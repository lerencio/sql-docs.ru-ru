---
title: Как просмотреть свойства экземпляра CDC | Документы Майкрософт
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4bce9b82-7bbd-41df-b3f4-4b40b8bad474
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eb49d9d3bc3b0c0ebc05b8c3e17b5a98c85c66e8
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86916528"
---
# <a name="how-to-view-the-cdc-instance-properties"></a>Как просмотреть свойства экземпляра CDC

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  Эта процедура описывает использование консоли конструктора CDC для просмотра сведений об экземплярах, создаваемых для поддержки управления работой экземпляров.  
  
### <a name="to-view-information-about-a-specific-instance"></a>Просмотр сведений об определенном экземпляре  
  
1.  В меню **Пуск** выберите **Консоль конструктора CDC**.  
  
2.  На панели слева разверните узел **Отслеживание измененных данных** , а затем разверните службу, содержащую экземпляр, данные которого необходимо просмотреть.  
  
3.  Выберите имя нужного экземпляра.  
  
     Сведения об экземпляре будут отображены в центральной части консоли конструктора CDC. Сведения разделены на четыре вкладки. Все вкладки доступны только для чтения.  
  
     **Состояние**  
     На этой вкладке отображаются сведения о текущем состоянии отслеживания измененных данных для экземпляра. Сведения о том, что отображено на этой вкладке, приведены в пункте **Вкладки средства просмотра** раздела [Manage a CDC Instance](../../integration-services/change-data-capture/manage-a-cdc-instance.md).  
  
     **Oracle**  
     На этой вкладке отображаются общие сведения об экземпляре CDC и базе данных-источнике Oracle. Сведения о том, что отображено на этой вкладке, приведены в разделе [Edit the Oracle Database Properties](../../integration-services/change-data-capture/edit-the-oracle-database-properties.md).  
  
     **Таблицы**  
     На этой вкладке отображаются сведения о таблицах, включенных в отслеживание измененных данных. На ней также указаны столбцы, состояние которых отслеживается. Сведения о том, что отображено на этой вкладке, приведены в разделе [Edit Tables](../../integration-services/change-data-capture/edit-tables.md).  
  
     **Дополнительно**  
     На этой вкладке приведен список дополнительных свойств, которые задаются в редакторе свойств. Сведения о том, что отображено на этой вкладке, приведены в разделе [Edit the Advanced Properties](../../integration-services/change-data-capture/edit-the-advanced-properties.md).  
  
  
