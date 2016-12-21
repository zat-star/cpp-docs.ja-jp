---
title: "コンパイラ エラー C3347 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3347"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3347"
ms.assetid: e939ad29-0b78-4681-9618-9bdae5675cee
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3347
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg': 必要な引数が属性 idl\_module 内で指定されていません  
  
 [idl\_module](../../windows/idl-module.md) 属性に必須の引数が渡されていません。  
  
 次の例では C3347 が生成されます。  
  
```  
// C3347.cpp // compile with: /c [module(name="xx")]; [idl_module(dllname="x")];    // C3347 // try the following line instead // [idl_module(name="test", dllname="x")];  
```