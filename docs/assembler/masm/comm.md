---
title: "COMM | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COMM"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMM directive"
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# COMM
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`definition` で指定された属性のコミューンの変数を作成します。  
  
## 構文  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## 解説  
 各 `definition` に次のフォームがあります :  
  
 \[入力\]*langtype*\[\] \[\[ **付近**  &#124; **この** \]**:**\[ *ラベル* \]`type`\[入力\]**:** *数* \]  
  
 *ラベルは* 変数の名前です。  `type` は型指定子 \([byte](../../assembler/masm/byte-masm.md)[word](../../assembler/masm/word.md) など\) またはバイト数を示す整数のいずれかです。   *数には* データ オブジェクトの数を指定します \(1 が既定値です。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)