---
title: "/DYNAMICBASE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/dynamicbase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DYNAMICBASE editbin オプション"
  - "DYNAMICBASE editbin オプション"
  - "-DYNAMICBASE editbin オプション"
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /DYNAMICBASE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ASLR \(Address Space Layout Randomization\) 機能を使用して、読み込み時に実行可能イメージをランダムに再ベースできるかどうかを指定します。  
  
## 構文  
  
```  
  
/DYNAMICBASE[:NO]  
```  
  
## 解説  
 既定では、リンカーは **\/DYNAMICBASE** オプションを設定します。  
  
 このオプションは、実行可能イメージのヘッダーを変更して、読み込み時に、ローダーがランダムにイメージを再ベースできるかどうかを示します。  
  
 ASLR は、Windows Vista、Windows Server 2008、Windows 7、Windows 8、および Windows Server 2012 でサポートされています。  
  
## 参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)   
 [Windows ISV Software Security Defenses](http://msdn.microsoft.com/library/bb430720.aspx)