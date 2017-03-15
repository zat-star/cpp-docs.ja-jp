---
title: ".SAVEREG | Microsoft Docs"
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
  - ".SAVEREG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SAVEREG directive"
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .SAVEREG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`UWOP_SAVE_NONVOL` を生成します。または`UWOP_SAVE_NONVOL_FAR` は現在のプロローグ オフセットを使用して指定のレジスタとオフセット \(`reg`\(\)`offset`\) のコードのエントリを戻すことができます。  MASM は、最も効率的なエンコーディングを選択します。  
  
## 構文  
  
```  
.SAVEREG reg, offset  
```  
  
## 解説  
 .SAVEREG は ml64.exe のユーザーがフレーム関数がどのように [PROC](../../assembler/masm/proc.md) フレームの宣言から [.ENDPROLOG](../Topic/.ENDPROLOG.md) のディレクティブまでのプロローグ内だけでアンワインドするかを指定できるようにします。  これらのディレクティブはコードを生成しません ; これらは `.xdata` と `.pdata` だけを生成します。  .SAVEREG はアンワインドされるアクションを実行する方法を指定する必要があります。  これは署名を確認するマクロでアンワインドするように指定することもアンワインド コードのディレクティブをラップすることをお勧めします。  
  
 詳細については、「[MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md)」を参照してください。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)