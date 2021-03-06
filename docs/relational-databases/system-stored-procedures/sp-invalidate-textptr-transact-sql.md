---
title: sp_invalidate_textptr (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_invalidate_textptr_TSQL
- sp_invalidate_textptr
dev_langs:
- TSQL
helpviewer_keywords:
- sp_invalidate_textptr
ms.assetid: dd9920e1-7064-4c05-93d8-9303103fa1d6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 269a49f76bd583c2233cf3720818590ca132c6a3
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85899408"
---
# <a name="sp_invalidate_textptr-transact-sql"></a>sp_invalidate_textptr (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Делает недействительным указанный указатель текста строки в транзакции или все подобные указатели. **sp_invalidate_textptr** можно использовать только для текстовых указателей в строке. Эти указатели относятся к таблицам, для которых включен параметр **text in row** .  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_invalidate_textptr [ [ @TextPtrValue = ] textptr_value ]  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @TextPtrValue = ] textptr_value`Указатель текста в строке, который должен быть недействительным. *textptr_value* имеет тип **varbinary (** 16 **)** и значение по умолчанию NULL. Если значение равно NULL, **sp_invalidate_textptr** делает недействительными все текстовые указатели в транзакции.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 0 (успешное завершение) или 1 (неуспешное завершение)  
  
## <a name="remarks"></a>Комментарии  
 В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] допустимо не более 1024 активных действительных указателя текста в строке на транзакцию на базу данных, однако транзакция, распространяющаяся более чем на одну базу данных, может иметь 1024 указателя текста в строке в каждой базе данных. **sp_invalidate_textptr** можно использовать для недействительности текстовых указателей в строке и, следовательно, свободного пространства для дополнительных текстовых указателей в строке.  
  
 Дополнительные сведения о параметре text in row см. в статье [sp_tableoption (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-tableoption-transact-sql.md).  
  
## <a name="permissions"></a>Разрешения  
 Необходимо быть членом роли **public**.  
  
## <a name="see-also"></a>См. также  
 [Ядро СУБД хранимых процедур &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)   
 [Системные хранимые процедуры &#40;&#41;Transact-SQL](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [sp_tableoption &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-tableoption-transact-sql.md)   
 [TEXTPTR &#40;Transact-SQL&#41;](../../t-sql/functions/text-and-image-functions-textptr-transact-sql.md)   
 [TEXTVALID (Transact-SQL)](../../t-sql/functions/text-and-image-functions-textvalid-transact-sql.md)  
  
  
