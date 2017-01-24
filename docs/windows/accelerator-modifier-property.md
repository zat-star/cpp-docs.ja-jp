---
title: "アクセラレータの [修飾子] プロパティ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Modifier プロパティ"
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# アクセラレータの [修飾子] プロパティ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アクセラレータ テーブルにある \[修飾子\] プロパティに有効なエントリは、次のとおりです。  
  
|値|Description|  
|-------|-----------------|  
|**なし**|ユーザーは \[キー\] の値だけを押します。  ASCII\/ANSI の値 \(001 ～ 026\) と共に使用すると、最も有効です。これらの値は、^A ～ ^Z \(Ctrl \+ A ～ Ctrl \+ Z\) として解釈されます。|  
|**Alt**|ユーザーは Alt キーを押して \[キー\] の値を押す必要があります。|  
|**Ctrl**|ユーザーは Ctrl キーを押して \[キー\] の値を押す必要があります。  ASCII タイプでは無効です。|  
|**Shift**|ユーザーは Shift キーを押して \[キー\] の値を押す必要があります。|  
|**Ctrl\+Alt**|ユーザーは Ctrl キーと Alt キーを押して \[キー\] の値を押す必要があります。  ASCII タイプでは無効です。|  
|**Ctrl\+Shift**|ユーザーは Ctrl キーと Shift キーを押して \[キー\] の値を押す必要があります。  ASCII タイプでは無効です。|  
|**Alt\+Shift**|ユーザーは Alt キーと Shift キーを押して \[キー\] の値を押す必要があります。  ASCII タイプでは無効です。|  
|**Ctrl\+Alt\+Shift**|ユーザーは Ctrl キー、Alt キー、および Shift キーを押して \[キー\] の値を押す必要があります。  ASCII タイプでは無効です。|  
  
## 要件  
 Win32  
  
## 参照  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Accelerator Editor](../Topic/Accelerator%20Editor.md)