---
title: Функции безопасности (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- functions [SQL Server], security
- security functions
- roles [SQL Server], functions
- users [SQL Server], security functions
- security [SQL Server], functions
ms.assetid: 7773a87d-2f1b-4951-a225-baf159a7291b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 6a97e7cde856f9f1cf6f7892a9f6cac9c03e338a
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87248498"
---
# <a name="security-functions-transact-sql"></a>Функции безопасности (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Следующие функции возвращают сведения, полезные для управления безопасностью. Дополнительные функции перечислены в статье [Криптографические функции (Transact-SQL)](../../t-sql/functions/cryptographic-functions-transact-sql.md).  
  
:::row:::
    :::column:::
        [CERTENCODED (Transact-SQL)](../../t-sql/functions/certencoded-transact-sql.md)
    :::column-end:::
    :::column:::
        [PWDCOMPARE (Transact-SQL)](../../t-sql/functions/pwdcompare-transact-sql.md)
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        [CERTPRIVATEKEY (Transact-SQL)](../../t-sql/functions/certprivatekey-transact-sql.md)
    :::column-end:::
    :::column:::
        [PWDENCRYPT (Transact-SQL)](../../t-sql/functions/pwdencrypt-transact-sql.md)
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        [CURRENT_USER (Transact-SQL)](../../t-sql/functions/current-user-transact-sql.md)
    :::column-end:::
    :::column:::
        [SCHEMA_ID (Transact-SQL)](../../t-sql/functions/schema-id-transact-sql.md)
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        [DATABASE_PRINCIPAL_ID (Transact-SQL)](../../t-sql/functions/database-principal-id-transact-sql.md)
    :::column-end:::
    :::column:::
        [SCHEMA_NAME (Transact-SQL)](../../t-sql/functions/schema-name-transact-sql.md)
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        [sys.fn_builtin_permissions (Transact-SQL)](../../relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql.md)
    :::column-end:::
    :::column:::
        [SESSION_USER (Transact-SQL)](../../t-sql/functions/session-user-transact-sql.md)
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        [sys.fn_get_audit_file (Transact-SQL)](../../relational-databases/system-functions/sys-fn-get-audit-file-transact-sql.md)
    :::column-end:::
    :::column:::
        [SUSER_ID (Transact-SQL)](../../t-sql/functions/suser-id-transact-sql.md)
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        [sys.fn_my_permissions (Transact-SQL)](../../relational-databases/system-functions/sys-fn-my-permissions-transact-sql.md)
    :::column-end:::
    :::column:::
        [SUSER_SID (Transact-SQL)](../../t-sql/functions/suser-sid-transact-sql.md)
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        [HAS_PERMS_BY_NAME (Transact-SQL)](../../t-sql/functions/has-perms-by-name-transact-sql.md)
    :::column-end:::
    :::column:::
        [SUSER_SNAME (Transact-SQL)](../../t-sql/functions/suser-sname-transact-sql.md)
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        [IS_MEMBER &#40;Transact-SQL&#41;](../../t-sql/functions/is-member-transact-sql.md)
    :::column-end:::
    :::column:::
        [SYSTEM_USER (Transact-SQL)](../../t-sql/functions/system-user-transact-sql.md)
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        [IS_ROLEMEMBER (Transact-SQL)](../../t-sql/functions/is-rolemember-transact-sql.md)
    :::column-end:::
    :::column:::
        [SUSER_NAME (Transact-SQL)](../../t-sql/functions/suser-name-transact-sql.md)
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        [Функция IS_SRVROLEMEMBER (Transact-SQL)](../../t-sql/functions/is-srvrolemember-transact-sql.md)
    :::column-end:::
    :::column:::
        [USER_ID (Transact-SQL)](../../t-sql/functions/user-id-transact-sql.md)
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        [ORIGINAL_LOGIN (Transact-SQL)](../../t-sql/functions/original-login-transact-sql.md)
    :::column-end:::
    :::column:::
        [USER_NAME (Transact-SQL)](../../t-sql/functions/user-name-transact-sql.md)
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        [PERMISSIONS (Transact-SQL)](../../t-sql/functions/permissions-transact-sql.md)
    :::column-end:::
    :::column:::
    :::column-end:::
:::row-end:::

&nbsp;
  
 Сведения о членстве в группах Windows см. в статьях [xp_logininfo (Transact-SQL)](../../relational-databases/system-stored-procedures/xp-logininfo-transact-sql.md) и [xp_enumgroups (Transact-SQL)](../../relational-databases/system-stored-procedures/xp-enumgroups-transact-sql.md).  
  
## <a name="see-also"></a>См. также:  
 [Хранимые процедуры безопасности (Transact-SQL)](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [Криптографические функции (Transact-SQL)](../../t-sql/functions/cryptographic-functions-transact-sql.md)   
 [Встроенные функции (Transact-SQL)](~/t-sql/functions/functions.md)   
 [Инструкции безопасности](https://msdn.microsoft.com/library/aebe2ec7-31bc-4697-a493-dcfcd0903a7b)  
  
  
