---
title: Элемент Banner
diagnose: In SQL Server, the Banner element identifies which utility generated the ssbdiagnose output XML file.
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- banner element
- XML output file format [ssbdiagnose], banner element
- ssbdiagnose
ms.assetid: cc6cd49a-acf0-4cfb-8c6a-554692b89de2
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: seo-lt-2019
ms.date: 03/01/2017
ms.openlocfilehash: bc2a4c5da5db899289b05845eaef1564437ef8c3
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85726819"
---
# <a name="banner-element-ssbdiagnose"></a>Элемент Banner (программа ssbdiagnose)


 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

Определяет программу, сформировавшую выходной XML-файл **ssbdiagnose** .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
<Banner  
    title="..."   
    product="..."   
    version="..." />  
```  
  
## <a name="element-attributes"></a>Атрибуты элемента  
  
|attribute|Description|  
|---------------|-----------------|  
|**title**|Определяет программу, сформировавшую выходной XML-файл **ssbdiagnose** .|  
|**product**|Определяет продукт, сформировавший выходной XML-файл **ssbdiagnose** .|  
|**version**|Определяет версию программы, которой был сформирован выходной XML-файл.|  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Description|  
|--------------------|-----------------|  
|**Тип данных и длина**|Нет.|  
|**Значение по умолчанию**|Нет.|  
|**Наличие**|Один раз в каждом выходном XML-файле программы **ssbdiagnose** .|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элементы|  
|------------------|--------------|  
|**Родительский элемент**|[Элемент DiagnosticInformation (программа ssbdiagnose)](../../tools/ssbdiagnose/diagnosticinformation-element-ssbdiagnose.md)|  
|**Дочерние элементы**|Нет.|  
  
## <a name="example"></a>Пример  
 Ниже приведен пример элемента Banner.  
  
```  
<Banner title="Service Broker Diagnostics Utility" product="Microsoft SQL Server" version="10.0.1073.0" />  
```  
  
## <a name="see-also"></a>См. также:  
 [Программа ssbdiagnose (компонент Service Broker)](../../tools/ssbdiagnose/ssbdiagnose-utility-service-broker.md)  
  
  
