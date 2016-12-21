---
title: "インライン アセンブラーのラベルにジャンプ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm キーワード [C++], ラベル"
  - "大文字と小文字の区別, インライン アセンブラー内のラベル"
  - "インライン アセンブラー, ジャンプ (ラベルに)"
  - "インライン アセンブラーのラベルにジャンプ"
  - "ラベル, __asm ブロック内"
  - "ラベル, インライン アセンブラー内"
ms.assetid: 36c18b97-8981-4631-9dfd-af6c14a04297
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# インライン アセンブラーのラベルにジャンプ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 通常 15 ので C または C\+\+ のラベルと同様に`__asm` ブロックのラベルに定義されている関数のスコープがあります \(ブロックでのみ\)。  アセンブリ命令と `goto` のステートメントはラベル内か `__asm` ブロックの外部にジャンプできます。  
  
 `__asm` ブロックで定義されたラベルは大文字と小文字の区別はありません ; `goto` ステートメントの両方とアセンブリ命令では大文字に関係なくそのラベルを表示できます。  C および C\+\+ のラベルは `goto` のステートメントで使用する場合にのみ大文字と小文字が区別されます。  アセンブリ命令は . ケースに関係なく C または C\+\+ のラベルにジャンプできます。  
  
 次のコードはすべての置換を示します :  
  
```  
void func( void )  
{  
   goto C_Dest;  /* Legal: correct case   */  
   goto c_dest;  /* Error: incorrect case */  
  
   goto A_Dest;  /* Legal: correct case   */  
   goto a_dest;  /* Legal: incorrect case */  
  
   __asm  
   {  
      jmp C_Dest ; Legal: correct case  
      jmp c_dest ; Legal: incorrect case  
  
      jmp A_Dest ; Legal: correct case  
      jmp a_dest ; Legal: incorrect case  
  
      a_dest:    ; __asm label  
   }  
  
   C_Dest:       /* C label */   
   return;  
}  
int main()  
{  
}  
```  
  
 `__asm` ブロックでラベルとして C ライブラリ関数の名前を使用しないでください。  たとえばラベルとして `exit` を使用するように次のよう誘惑されることがあります :  
  
```  
; BAD TECHNIQUE: using library function name as label  
jne exit  
   .  
   .  
   .  
exit:  
   ; More __asm code follows  
```  
  
 **終了**  . 関数が C\+\+ ライブラリの名前であるためこのコードは希望する位置ではなく  **終了**  の関数にジャンプが発生することがあります。  
  
 MASM のプログラムと同様にドル記号 \(\)`$` カウンターは現在の場所として機能します。  ではアセンブルする手順のラベルです。  `__asm` ブロックでは主要な使用方法は条件付き飛越をに設定することです :  
  
```  
jne $+5 ; next instruction is 5 bytes long  
jmp farlabel  
; $+5  
   .  
   .  
   .  
farlabel:  
```  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)