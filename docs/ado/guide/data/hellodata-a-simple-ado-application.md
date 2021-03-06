---
title: 'HelloData: простое приложение ADO | Документация Майкрософт'
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- HelloData sample application [ADO]
- ADO, samples
ms.assetid: de4bcd56-dac2-45e6-95ab-9fd7f25878fc
author: rothja
ms.author: jroth
ms.openlocfilehash: 18f9f0cd227a258b1d2d9cd2d201527f614bcc49
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82758830"
---
# <a name="hellodata-a-simple-ado-application"></a>HelloData: простое приложение ADO
Это простое приложение проходит через каждую из четырех основных операций ADO: получение, изучение, изменение и обновление данных. Эти операции выполняются с примером базы данных Northwind, входящей в состав SQL Server Microsoft®. Чтобы сосредоточиться на основных принципах работы с ADO и избежать загромождения кода, обработка ошибок в примере минимальна.  
  
### <a name="to-run-hellodata"></a>Запуск HelloData  
  
1.  Создайте новый стандартный проект Visual Basic EXE, который ссылается на библиотеку ADO. Дополнительные сведения см. [в разделе ссылки на библиотеки ADO](../../../ado/guide/referencing-the-ado-libraries.md).  
  
2.  Создайте четыре кнопки в верхней части формы, задав свойства **Name** и **Caption** в значениях, приведенных в таблице в конце этого раздела.  
  
3.  Под кнопками добавьте **элемент управления Microsoft DataGrid** (мсдатгрд. ocx). Файл Мсдатгрд. ocx входит в состав Visual Basic и находится в каталоге \Windows\System32. или \Winnt\System32. Чтобы добавить элемент управления DataGrid в панель элементов Visual Basic, выберите **компоненты...** в меню **проект** . Установите флажок рядом с элементом Microsoft DataGrid Control 6,0 (с пакетом обновления 3 (SP3)) и нажмите кнопку **ОК**. Чтобы добавить элемент управления в проект, перетащите элемент управления DataGrid из панели элементов в форму Visual Basic.  
  
4.  Создайте **текстовое поле** в форме под сеткой и задайте его свойства, как показано в таблице. По завершении форма должна выглядеть примерно так, как показано на следующем рисунке.  
  
5.  Наконец, скопируйте код, указанный в [коде HelloData](../../../ado/guide/data/hellodata-code.md), и вставьте его в окно редактора кода в форме. Нажмите клавишу **F5** , чтобы выполнить код.  
  
> [!NOTE]
>  В приведенном ниже примере и в рамках этого руководством для проверки подлинности на сервере используется идентификатор пользователя «MyId» с паролем «123aBc». Эти значения следует заменить действительными учетными данными для входа на сервер. Кроме того, замените значение "MySQLServer" именем сервера.  
  
 Подробное описание кода см. [в разделе Comments on HelloData](../../../ado/guide/data/comments-on-hellodata.md).  
  
 ![Форма Form1 для приложения HelloData VB](../../../ado/guide/data/media/hellodata.gif "HelloData")  
  
|Тип элемента управления|Свойство|Значение|  
|------------------|--------------|-----------|  
|Form|name|Form1|  
||Высота:|6500|  
||По ширине|6500|  
|Microsoft DataGrid|name|grdDisplay1|  
|TextBox|name|txtDisplay1|  
||Multiline|true|  
|Кнопка команды|name|кмджетдата|  
||Caption|Получение данных|  
|Кнопка команды|name|кмдексаминедата|  
||Caption|Проверка данных|  
|Кнопка команды|name|кмдедитдата|  
||Caption| Изменение данных|  
|Кнопка команды|name|кмдупдатедата|  
||Caption|Обновление данных|
