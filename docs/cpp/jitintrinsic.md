---
title: "jitintrinsic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "jitintrinsic"
  - "jitintrinsic_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++], jitintrinsic"
  - "jitintrinsic __declspec 修飾子"
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# jitintrinsic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

64 ビット共通言語ランタイムにとって重要であると関数をマークします。  これは、Microsoft が提供するライブラリの特定の関数で使用されます。  
  
## 構文  
  
```  
__declspec(jitintrinsic)  
```  
  
## 解説  
 `jitintrinsic` は、関数シグネチャに MODOPT \(<xref:System.Runtime.CompilerServices.IsJitIntrinsic>\) を追加します。  
  
 予期しない結果が発生する可能性があるため、ユーザーはこの `__declspec` 修飾子を使用しないでください。  
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)