---
title: Источник Oracle
ms.custom: ''
ms.date: 08/14/2019
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6260504afcaabfefb6de7e6f262aa475479cf487
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86913768"
---
# <a name="oracle-source"></a>Источник Oracle

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]

Источник Oracle извлекает данные из Oracle Database в таких режимах:

- Таблица или представление.

- Результат выполнения инструкции SQL.

Для подключения к источнику Oracle используется диспетчер подключений Oracle. Дополнительные сведения см. в статье о [диспетчере подключений Oracle](oracle-connection-manager.md).

## <a name="error-output"></a>Вывод ошибок

Выходные данные об ошибках представлены в таких столбцах:  

- **Код ошибки.** Номер, обозначающий тип текущей ошибки. Код ошибки может быть получен из таких источников:
    - Сервер Oracle. Подробное описание ошибки см. в документации по базе данных Oracle.
    - Среда выполнения Integration Services. Список кодов ошибок служб SSIS см. в «Справочнике по кодам ошибок и сообщениям служб SIS».
- **Столбец с ошибкой.** Номер исходного столбца, который вызывает ошибки преобразования.

- **Столбцы данных с ошибкой.** Данные, вызвавшие ошибку.

В выходных данных об ошибках источник Oracle возвращает сведения об ошибках, возникших в процессе загрузки и извлечения. Дополнительные сведения см. далее в разделе о [странице вывода ошибок](#oracle-source-editor-error-output-page).

## <a name="troubleshooting-the-oracle-source"></a>Устранение неполадок с источником Oracle

Устранять неполадки с экспортом данных можно с помощью журнала вызовов ODBC, которые источник Oracle отправляет к источникам данных Oracle. Для ведения журнала вызовов ODBC к источникам данных Oracle, выполняемых источником Oracle, включите трассировку диспетчера драйверов ODBC. Дополнительные сведения см. в документации Майкрософт по теме *Как формировать трассировку ODBC с помощью администратора источника данных ODBC*.

## <a name="oracle-source-custom-properties"></a>Настраиваемые свойства источника Oracle

Ниже приведены настраиваемые свойства источника Oracle. Все свойства доступны для чтения и записи.

|Имя свойства|Тип данных|Описание|
|:-|:-|:-|
|AccessMode|Integer (перечисление)|Режим, используемый для доступа к базе данных. Возможные значения — **Имя таблицы** и **Команда SQL**. По умолчанию применяется значение **Имя таблицы**.|
|BatchSize|Целое число|Размер пакета для массовой загрузки. Это количество записей, извлекаемых в виде массива. <br>Это свойство можно задать только в диалоговом окне **Расширенный редактор**.|
|DefaultCodePage|Целое число|Кодовая страница, которая используется, если для источника данных нет сведений о кодовой странице. <br>Это свойство можно задать только в диалоговом окне **Расширенный редактор**.|
|PreFetchCount|Целое число|Количество предварительно получаемых строк. <br>Это свойство можно задать только в диалоговом окне **Расширенный редактор**.|
|SqlCommand|Строка|Команда SQL, которая должна быть выполнена, если для AccessMode задано значение «команда SQL».|
|TableName|Строка|Имя используемой таблицы с данными, если для AccessMode задано значение "Имя таблицы".|

## <a name="configuring-the-oracle-source"></a>Настройка источника Oracle

Источник Oracle можно настроить программно или с помощью конструктора Integration Services.

Редактор источника Oracle показан на рисунке ниже. Он содержит страницу диспетчера подключений, страницу столбцов и страницу вывода ошибок.

Дополнительные сведения см. в одном из следующих разделов:

- [Редактор источника Oracle (страница диспетчера подключений)](#oracle-source-editor-connection-manager-page)
- [Редактор источника Oracle (страница столбцов)](#oracle-source-editor-columns-page)
- [Редактор источника Oracle (страница вывода ошибок)](#oracle-source-editor-error-output-page)

![Источник Oracle](media/oracle-source.png)

Диалоговое окно **Расширенный редактор** содержит свойства, которые можно задавать программным путем.

Открытие диалогового окна **Расширенный редактор** .

- На экране **Поток данных** проекта Integration Services щелкните правой кнопкой мыши источник Oracle и выберите пункт **Показать расширенный редактор**.

Дополнительные сведения о свойствах, которые можно задать в диалоговом окне **Расширенный редактор**, см. в разделе [Настраиваемые свойства источника Oracle](#oracle-source-custom-properties).

## <a name="oracle-source-editor-connection-manager-page"></a>Редактор источника Oracle (страница диспетчера подключений)

На странице **Диспетчер подключений** диалогового окна **Редактор источника Oracle** можно выбрать Oracle Database в качестве источника, таблицы или представления из базы данных.

**Чтобы открыть страницу диспетчера подключений в редакторе источника Oracle, сделайте следующее:**

- В SQL Server Data Tools откройте пакет SQL Server Integration Services (SSIS) с источником Oracle.

- На вкладке "Поток данных" дважды щелкните источник Oracle.
### <a name="options"></a>Параметры

**Connection manager**

Выберите в списке существующий диспетчер подключений или нажмите кнопку **Создать**, чтобы создать диспетчер подключений Oracle.

**Создать**

Нажмите кнопку **Создать**. Откроется диалоговое окно **Редактор диспетчера подключений Oracle**, где можно создать диспетчер подключений.

**Режим доступа к данным**

Выберите метод выбора данных из источника. Доступные параметры показаны в следующей таблице.

|Параметр|Описание|
|:-|:-|
|Таблица или представление|Получение данных из таблицы или представления в источнике данных Oracle. Если выбран этот параметр, щелкните доступную таблицу или представление в списке **Имя таблицы или представления**.|
|Команда SQL|Получение данных из источника данных Oracle с помощью SQL-запроса. Если выбран этот параметр, введите запрос одним из следующих способов: <br>Введите текст SQL-запроса в поле **Текст команды SQL** . <br>Нажмите кнопку **Обзор** , чтобы загрузить SQL-запрос из текстового файла. <br>Чтобы проверить синтаксис текста запроса, нажмите кнопку **Анализ запроса** .|

**Предварительный просмотр**

Нажмите кнопку **Просмотр** , чтобы просмотреть первые 200 строк данных, извлеченных из выбранной таблицы или представления.

## <a name="oracle-source-editor-columns-page"></a>Редактор источника Oracle (страница столбцов)

Страница **Столбцы** диалогового окна **Редактор источника Oracle** используется для сопоставления выходного столбца с каждым внешним (исходным) столбцом.

**Чтобы открыть страницу столбцов в редакторе источника Oracle, сделайте следующее:**

- В SQL Server Data Tools откройте пакет SQL Server Integration Services (SSIS) с источником Oracle.

- На вкладке "Поток данных" дважды щелкните источник Oracle.

- В редакторе источника Oracle щелкните "Столбцы".

### <a name="options"></a>Параметры

**Доступные внешние столбцы**

Список доступных внешних столбцов, которые можно выбрать для добавления в список **Внешний столбец**, упорядоченный в том порядке, в котором они выбраны. В этой таблице нельзя добавлять или удалять столбцы.

Чтобы выбрать все столбцы, установите флажок **Выделить все**.

**Внешние столбцы**

Выбранные внешние (исходные) столбцы перечисляются по порядку.
Чтобы изменить порядок, сначала очистите список "Доступные внешние столбцы", а затем выберите столбцы в другом порядке.

**Выходной столбец**

Имя выбранного внешнего (исходного) столбца — это имя выходного столбца, используемое по умолчанию. Вы можете указать любое уникальное имя.
> [!NOTE]
>
>Если есть столбцы с неподдерживаемыми типами данных, выводится предупреждение о том, что такие типы данных не поддерживаются, а соответствующие столбцы удаляются из списка столбцов сопоставления.

## <a name="oracle-source-editor-error-output-page"></a>Редактор источника Oracle (страница вывода ошибок)

На странице **Вывод ошибок** диалогового окна **Редактор источника Oracle** можно выбрать параметры обработки ошибок.

**Чтобы открыть страницу вывода ошибок в редакторе источника Oracle, сделайте следующее:**

- В SQL Server Data Tools откройте пакет SQL Server Integration Services (SSIS) с источником Oracle.

- На вкладке "Поток данных" дважды щелкните источник Oracle.

- В редакторе источника Oracle щелкните "Вывод ошибок".

### <a name="options"></a>Параметры

**Действия при ошибке**

Выберите способ обработки ошибок в потоке источником Oracle: пропустить ошибку, перенаправить строку или вызвать сбой компонента.
**Дополнительные сведения см. в статье** [Обработка ошибок в данных](https://docs.microsoft.com/sql/integration-services/data-flow/error-handling-in-data?view=sql-server-2017)

**Усечение**

Выберите порядок обработки усечений в потоке источником Oracle: пропустить ошибку, перенаправить строку или вызвать сбой компонента.

## <a name="next-steps"></a>Дальнейшие действия

- Настройка [назначения Oracle](oracle-destination.md).
- Если у вас возникнут вопросы, посетите страницу [технического сообщества](https://aka.ms/AA5u35j).
