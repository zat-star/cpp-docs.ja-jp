---
title: ".SAVEXMM128 | Microsoft Docs"
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
  - ".SAVEXMM128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SAVEXMM128 directive"
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .SAVEXMM128
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`UWOP_SAVE_XMM128` を生成します。または`UWOP_SAVE_XMM128_FAR` は現在のプロローグ オフセットを使用して指定の XMM レジスタのコード エントリとオフセットに戻すことができます。  MASM は、最も効率的なエンコーディングを選択します。  
  
## 構文  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## 解説  
 .SAVEXMM128 は ml64.exe のユーザーがで指定したフレーム関数を呼び出す終了すると[PROC](../../assembler/masm/proc.md) フレームの宣言から [.ENDPROLOG](../Topic/.ENDPROLOG.md) のディレクティブまでプロローグ内でのみ使用できます。  これらのディレクティブはコードを生成しません ; これらは `.xdata` と `.pdata` だけを生成します。  .SAVEXMM128 はアンワインドされるアクションを実行する方法を指定する必要があります。  これは署名を確認するマクロでアンワインドするように指定することもアンワインド コードのディレクティブをラップすることをお勧めします。  
  
 `offset` は 16 の倍数である必要があります。  
  
 詳細については、「[MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md)」を参照してください。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)