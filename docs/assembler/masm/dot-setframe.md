---
title: ".SETFRAME | Microsoft Docs"
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
  - ".SETFRAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SETFRAME directive"
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .SETFRAME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定 `reg` 登録 \(\) を使用してアンワインド情報のフレーム レジスタ フィールドとオフセットとオフセット \(`offset`\) を入力します。  オフセットは 16 の倍数で、240 以下である必要があります。  このディレクティブは現在のプロローグ オフセットを使用して `UWOP_SET_FPREG` アンワインド指定されたレジスタのコード エントリを生成します。  
  
## 構文  
  
```  
.SETFRAME reg, offset  
```  
  
## 解説  
 .SETFRAME は ml64.exe のユーザーがで指定したフレーム関数を呼び出す終了すると[PROC](../../assembler/masm/proc.md) フレームの宣言から [.ENDPROLOG](../Topic/.ENDPROLOG.md) のディレクティブまでプロローグ内でのみ使用できます。  これらのディレクティブはコードを生成しません ; これらは `.xdata` と `.pdata` だけを生成します。  .SETFRAME はアンワインドされるアクションを実行する方法を指定する必要があります。  これは署名を確認するマクロでアンワインドするように指定することもアンワインド コードのディレクティブをラップすることをお勧めします。  
  
 詳細については、「[MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md)」を参照してください。  
  
## サンプル  
  
### Description  
 次の例ではフレーム ポインターを使用する方法を示します :  
  
### コード  
  
```  
; ml64 frmex2.asm /link /entry:frmex2 /SUBSYSTEM:CONSOLE  
_text SEGMENT  
frmex2 PROC FRAME  
   push rbp  
.pushreg rbp  
   sub rsp, 010h  
.allocstack 010h  
   mov rbp, rsp  
.setframe rbp, 0  
.endprolog  
   ; modify the stack pointer outside of the prologue (similar to alloca)  
   sub rsp, 060h  
  
   ; we can unwind from the following AV because of the frame pointer     
   mov rax, 0  
   mov rax, [rax] ; AV!  
  
   add rsp, 060h  
   add rsp, 010h  
   pop rbp  
   ret  
frmex2 ENDP  
_text ENDS  
END  
```  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)