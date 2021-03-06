---
title: Создание учетных данных для SQLRUserGroup
description: Для соединений с замыканием на себя, использующих неявную проверку подлинности, создайте имя входа в SQL Server для SQLRUserGroup, чтобы учетная запись рабочей роли могла войти на сервер для преобразования идентификатора в вызывающего пользователя.
ms.prod: sql
ms.technology: machine-learning
ms.date: 01/25/2019
ms.topic: conceptual
author: dphansen
ms.author: davidph
monikerRange: '>=sql-server-2016||>=sql-server-linux-ver15||=sqlallproducts-allversions'
ms.openlocfilehash: c57a62e954ae8cb0fc52c9a5ead22d418243c0b8
ms.sourcegitcommit: 68583d986ff5539fed73eacb7b2586a71c37b1fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/04/2020
ms.locfileid: "81117127"
---
# <a name="create-a-login-for-sqlrusergroup"></a>Создание учетных данных для SQLRUserGroup
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

Создайте [имя входа в SQL Server](https://docs.microsoft.com/sql/relational-databases/security/authentication-access/create-a-login) для [SQLRUserGroup](../concepts/security.md#sqlrusergroup), когда [соединение с замыканием на себя](../../machine-learning/concepts/security.md#implied-authentication) в скрипте указывает *доверенное подключение* и удостоверение, используемое для выполнения объекта, содержит код учетной записи пользователя Windows.

Доверенные соединения — это те, которые имеют `Trusted_Connection=True` в строке подключения. Когда SQL Server получает запрос, указывающий на доверенное соединение, он проверяет, имеет ли удостоверение текущего пользователя Windows имя входа. Для внешних процессов, выполняющихся в качестве учетной записи рабочей роли (например, MSSQLSERVER01 из **SQLRUserGroup**), запрос завершается сбоем, так как по умолчанию у этих учетных записей нет имени входа.

Можно обойти ошибку подключения, создав имя входа для **SQLServerRUserGroup**. Дополнительные сведения об удостоверениях и внешних процессах см. в разделе [Общие сведения о безопасности для платформы расширяемости](../concepts/security.md).

> [!Note]
> Убедитесь, что **SQLRUserGroup** имеет разрешения "Локальный вход в систему". По умолчанию это право предоставляется всем новым локальным пользователям, но некоторые более строгие политики групп в организации могут отключить это право.

## <a name="create-a-login"></a>Создает вход

1. В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]в обозревателе объектов разверните узел **Безопасность**, щелкните правой кнопкой мыши **Имена входа**и выберите пункт **Создать имя входа**.

2. В диалоговом окне **Создание имени входа** нажмите кнопку **Поиск**. (Пока не вводите ничего в поле.)
    
     ![Нажмите кнопку "Поиск", чтобы добавить новое имя входа для машинного обучения](media/implied-auth-login1.png "Нажмите кнопку "Поиск", чтобы добавить новое имя входа для машинного обучения")

3. В поле **Выбрать пользователя или группу** нажмите кнопку **Типы объектов**.

     ![Выполните поиск типов объектов, чтобы добавить новое имя входа для машинного обучения](media/implied-auth-login2.png "Выполните поиск типов объектов, чтобы добавить новое имя входа для машинного обучения")

4. В диалоговом окне **Типы объектов** выберите **Группы**. Очистите все флажки.

     ![Выберите "Группы" в диалоговом окне "Типы объектов"](media/implied-auth-login3.png "Выберите "Группы" в диалоговом окне "Типы объектов"")

4. Щелкните **Дополнительные**, убедитесь, что поиск выполняется в текущем компьютере, и нажмите **Найти**.

     ![Нажмите кнопку "Найти", чтобы получить список групп](media/implied-auth-login4.png "Нажмите кнопку "Найти", чтобы получить список групп")

5. Прокрутите список учетных записей групп на сервере, пока не найдете учетную запись, которая начинается с `SQLRUserGroup`.
    
    + Имя группы, связанной со службой панели запуска для _экземпляра по умолчанию_ всегда **SQLRUserGroup**, независимо от того, установлен ли R или Python или оба. Выберите эту учетную запись только для экземпляра по умолчанию.
    + Если вы используете _именованный экземпляр_, имя экземпляра добавляется к имени рабочей группы по умолчанию — `SQLRUserGroup`. Например, если экземпляру присвоено имя MLTEST, то именем группы пользователей по умолчанию для этого экземпляра будет **SQLRUserGroupMLTest**.
 
    ![Пример групп на сервере](media/implied-auth-login5.png "Пример групп на сервере")
   
5. Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно поиска.

    > [!IMPORTANT]
    > Убедитесь, что выбрана правильная учетная запись для экземпляра. Каждый экземпляр может использовать только собственную службу панели запуска и группу, созданную для этой службы. Экземпляры не могут совместно использовать службу панели запуска или учетные записи рабочей роли.

6. Нажмите кнопку **ОК** еще раз, чтобы закрыть диалоговое окно **Выбор пользователя или группы**.

7. В диалоговом окне **Создание имени входа** нажмите кнопку **ОК**. По умолчанию имя входа назначается **общедоступной** роли и имеет разрешение на подключение к ядру СУБД.

## <a name="next-steps"></a>Дальнейшие действия

+ [Общие сведения о безопасности](../concepts/security.md)
+ [Платформа расширяемости](../concepts/extensibility-framework.md)
