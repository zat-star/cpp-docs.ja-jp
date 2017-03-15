---
title: "生の擬似演算 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4def1a0e-ec28-4736-91fb-fac95fba1f36
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# 生の擬似演算
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、擬似演算の一覧を示します。  
  
## 解説  
  
|擬似演算|説明|  
|----------|--------|  
|PROC FRAME \[:ehandler\]|この演算を使用すると、MASM が、関数の構造化例外処理のアンワインド動作のために .pdata に関数テーブル エントリ、.xdata にアンワイド情報を生成します。  ehandler を指定すると、言語固有のハンドラーとして .xdata にこのプロセスが入力されます。<br /><br /> FRAME 属性を使用する場合、.ENDPROLOG ディレクティブの前に FRAME 属性を置く必要があります。  関数がリーフ関数 \([関数の型](../build/function-types.md) で定義\) の場合、これらの擬似演算以外の擬似演算と同様、FRAME 属性は必要ありません。|  
|.PUSHREG reg|プロローグ内の現在のオフセットを使用して、指定のレジスタ番号に対して UWOP\_PUSH\_NONVOL アンワインド コード エントリを生成します。<br /><br /> これは、不揮発性整数レジスタだけで使用できます。  揮発性レジスタのプッシュでは、代わりに .ALLOCSTACK 8 を使用してください。|  
|.SETFRAME reg, offset|指定のレジスタとオフセットを使用してアンワインド情報のフレーム レジスタ フィールドとオフセットを設定します。  オフセットは 16 の倍数で、240 以下である必要があります。  また、このディレクティブは、現在のプロローグ オフセットを使用して指定のレジスタに対して UWOP\_SET\_FPREG アンワインド コード エントリも生成します。|  
|.ALLOCSTACK size|プロローグ内に指定されている現在のオフセット サイズで、UWOP\_ALLOC\_SMALL または UWOP\_ALLOC\_LARGE を生成します。<br /><br /> size オペランドは 8 の倍数である必要があります。|  
|.SAVEREG reg, offset|現在のプロローグ オフセットを使用して指定のレジスタとオフセットに対して UWOP\_SAVE\_NONVOL または UWOP\_SAVE\_NONVOL\_FAR のいずれかのアンワインド コード エントリを生成します。  MASM は、最も効率的なエンコーディングを選択します。<br /><br /> オフセットは、正の数値で、8 の倍数であることが必要です。  オフセットは、プロシージャのフレームの基底からの相対値です。プロシージャのフレームの基底は、通常 RSP 内にありますが、フレーム ポインターを使用する場合は、スケールされないフレーム ポインターになります。|  
|.SAVEXMM128 reg, offset|現在のプロローグ オフセットを使用して指定の XMM レジスタとオフセットに対して UWOP\_SAVE\_XMM128 または UWOP\_SAVE\_XMM128\_FAR のいずれかのアンワインド コード エントリを生成します。  MASM は、最も効率的なエンコーディングを選択します。<br /><br /> オフセットは、正の数値で、8 の倍数であることが必要です。  オフセットは、プロシージャのフレームの基底からの相対値です。プロシージャのフレームの基底は、通常 RSP 内にありますが、フレーム ポインターを使用する場合は、スケールされないフレーム ポインターになります。|  
|.PUSHFRAME \[code\]|UWOP\_PUSH\_MACHFRAME アンワインド コード エントリを生成します。  オプションのコードが指定されている場合、アンワインド コード エントリに修飾子 1 が付きます。  それ以外の場合、修飾子は 0 になります。|  
|.ENDPROLOG|プロローグ宣言の終了を示します。  関数の最初の 255 バイトで発生する必要があります。|  
  
 ほとんどのオペコードを適切に使用したサンプル関数プロローグを次に示します。  
  
```  
sample PROC FRAME     
   db      048h; emit a REX prefix, to enable hot-patching  
push rbp  
.pushreg rbp  
sub rsp, 040h  
.allocstack 040h     
lea rbp, [rsp+020h]  
.setframe rbp, 020h  
movdqa [rbp], xmm7  
.savexmm128 xmm7, 020h;the offset is from the base of the frame  
;not the scaled offset of the frame  
mov [rbp+018h], rsi  
.savereg rsi, 038h  
mov [rsp+010h], rdi  
.savereg rdi, 010h; you can still use RSP as the base of the frame  
; or any other register you choose  
.endprolog  
  
; you can modify the stack pointer outside of the prologue (similar to alloca)  
; because we have a frame pointer.  
; if we didn’t have a frame pointer, this would be illegal  
; if we didn’t make this modification,  
; there would be no need for a frame pointer  
  
sub rsp, 060h  
  
; we can unwind from the following AV because of the frame pointer  
  
mov rax, 0  
mov rax, [rax] ; AV!  
  
; restore the registers that weren’t saved with a push  
; this isn’t part of the official epilog, as described in section 2.5  
  
movdqa xmm7, [rbp]  
mov rsi, [rbp+018h]  
mov rdi, [rbp-010h]  
  
; Here’s the official epilog  
  
lea rsp, [rbp-020h]  
pop rbp  
ret  
sample ENDP  
```  
  
## 参照  
 [MASM のアンワインド ヘルパー](../build/unwind-helpers-for-masm.md)