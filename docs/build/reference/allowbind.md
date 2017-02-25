---
title: "/ALLOWBIND | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/allowbind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALLOWBIND editbin オプション"
  - "/ALLOWBIND editbin オプション"
  - "-ALLOWBIND editbin オプション"
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /ALLOWBIND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DLL をバインドすることができるかどうかを指定します。  
  
```  
  
/ALLOWBIND[:NO]  
  
```  
  
## 解説  
 イメージをバインドするように Bind.exe に示す DLL のヘッダーの **\/ALLOWBIND** のオプションが小さい。  バインドは、ローダーが必要再ベース高速読み込み、それぞれの参照される DLL のアドレスのフィックスアップを要求する場合にイメージを実行してから。  これはデジタル署名にバインディング無効にするシグネチャを DLL にバインドされてしない場合があります。  バインドは ASLR \(ASLR\) がイメージに対して ASLR 機能をサポートする Windows のバージョンの **\/DYNAMICBASE** を使用して有効に影響しません。  
  
 Bind.exe が DLL をバインドするのを防ぐことが **\/ALLOWBIND:NO** を使用します。  
  
 詳細については、[\/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md) のリンカー オプションを参照します。  
  
## 参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)