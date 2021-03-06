---
title: Шаг 3. Тестирование пакета, созданного на занятии 6 | Документация Майкрософт
ms.custom: ''
ms.date: 01/11/2019
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: tutorial
ms.assetid: c184c92d-948f-4037-a502-5fabd909c84c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dec02c9a17a2eb1db3411c9b359ad55a83ac4fa5
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86922374"
---
# <a name="lesson-6-3-test-the-lesson-6-package"></a>Занятие 6-3. Тестирование пакета занятия 6

[!INCLUDE[sqlserver-ssis](../includes/applies-to-version/sqlserver-ssis.md)]


Во время выполнения пакет получает значение для свойства **Каталог** из параметра **VarFolderName**.  
  
Чтобы убедиться в том, что пакет обновляет свойство **Каталог**, выполните пакет. Так как в новый каталог были скопированы три файла образцов данных, поток данных запускается три раза.
  
## <a name="check-the-package-layout"></a>Проверка макета пакета  
Прежде чем проверить пакет, нужно убедиться в том, что потоки данных и управления в пакете занятия 6 аналогичны объектам, показанным на следующих схемах:   
  
**Поток управления**  
  
![Поток управления](../integration-services/media/task4lesson2control.gif "Поток управления")  
  
**Поток данных**  
  
![Поток данных](../integration-services/media/task5lesson5data.gif "Поток данных")  
  
## <a name="test-the-lesson-6-package"></a>Тестирование пакета занятия 6  
  
1.  В меню **Отладка** выберите команду **Начать отладку**.  
  
2.  После окончания работы пакета выберите в меню **Отладка** пункт **Остановить отладку**.  
  
## <a name="go-to-next-task"></a>Переход к следующей задаче
[Шаг 4. Развертывание пакета занятия 6](../integration-services/lesson-6-4-deploying-the-lesson-6-package.md)  
  
  
  
