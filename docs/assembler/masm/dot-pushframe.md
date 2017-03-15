---
title: ".PUSHFRAME | Microsoft Docs"
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
  - ".PUSHFRAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".PUSHFRAME directive"
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .PUSHFRAME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`UWOP_PUSH_MACHFRAME` アンワインド コード エントリを生成します。  省略可能な `code` が指定されている場合アンワインド コード エントリは 1. で修飾子です。  それ以外の場合、修飾子は 0 になります。  
  
## 構文  
  
```  
.PUSHFRAME [code]  
```  
  
## 解説  
 .PUSHFRAME は ml64.exe のユーザーがフレーム関数がどのように [PROC](../../assembler/masm/proc.md) フレームの宣言から [.ENDPROLOG](../Topic/.ENDPROLOG.md) のディレクティブまでのプロローグ内だけでアンワインドするかを指定できるようにします。  これらのディレクティブはコードを生成しません ; これらは `.xdata` と `.pdata` だけを生成します。  .PUSHFRAME はアンワインドされるアクションを実行する方法を指定する必要があります。  これは署名を確認するマクロでアンワインドするように指定することもアンワインド コードのディレクティブをラップすることをお勧めします。  
  
 詳細については、「[MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md)」を参照してください。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)