---
title: "プロローグ/エピローグ コードの記述時の考慮事項 | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "__LOCAL_SIZE 定数"
  - "レイアウト, スタック フレーム"
  - "スタック フレームのレイアウト"
  - "スタック, スタック フレームのレイアウト"
ms.assetid: 3b8addec-e809-48e4-b1d0-5bad133bd4b8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロローグ/エピローグ コードの記述時の考慮事項
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 独自のプロローグとエピローグのコード シーケンスを記述する前に、スタック フレームがどのように配置されるかを理解することが重要です。  **\_\_LOCAL\_SIZE** 事前定義済み定数の使用方法も知っておくと便利です。  
  
##  <a name="_clang_c_stack_frame_layout"></a> C のスタック フレームのレイアウト  
 この例は、32 ビット関数で使用される標準プロローグ コードを示しています。  
  
```  
push     ebp                 ; Save ebp  
mov      ebp, esp            ; Set stack frame pointer  
sub      esp, localbytes     ; Allocate space for locals  
push     <registers>         ; Save registers  
```  
  
 `localbytes` 変数は、ローカル変数のスタックで必要なバイト数を表します。また、`registers` 変数は、スタックに格納されるレジスタの一覧を表すプレースホルダーです。  レジスタをプッシュした後、スタックに他の適切なデータを配置できます。  対応するエピローグ コードは次のとおりです。  
  
```  
pop      <registers>         ; Restore registers  
mov      esp, ebp            ; Restore stack pointer  
pop      ebp                 ; Restore ebp  
ret                          ; Return from function  
```  
  
 スタックは、常に下に \(上位メモリ アドレスから下位メモリ アドレスに\) 向かって大きくなります。  基本ポインター \(`ebp`\) は、プッシュされた `ebp` の値を指します。  ローカル変数領域は `ebp-2` から始まります。  ローカル変数にアクセスするには、`ebp` からのオフセットを計算します。そのためには、`ebp` から適切な値を減算します。  
  
##  <a name="_clang_the___local_size_constant"></a> \_\_LOCAL\_SIZE 定数  
 コンパイラには、関数プロローグ コードのインライン アセンブラー ブロックで使用できる定数、**\_\_LOCAL\_SIZE** が用意されています。  この定数は、カスタム プロローグ コードでスタック フレームのローカル変数領域を割り当てるために使用されます。  
  
 **\_\_LOCAL\_SIZE** の値は、コンパイラによって決定されます。  値は、すべてのユーザー定義のローカル変数とコンパイラにより生成された一時変数の合計バイト数です。  **\_\_LOCAL\_SIZE** は、イミディエイト \(即値\) オペランドとしてのみ使用できます。式では使用できません。  この定数の値は、変更することも再定義することもできません。  次に例を示します。  
  
```  
mov      eax, __LOCAL_SIZE           ;Immediate operand--Okay  
mov      eax, [ebp - __LOCAL_SIZE]   ;Error  
```  
  
 カスタムのプロローグ シーケンスとエピローグ シーケンスを含む naked 関数の次の例では、プロローグ シーケンスで **\_\_LOCAL\_SIZE** を使用しています。  
  
```  
__declspec ( naked ) func()  
{  
   int i;  
   int j;  
  
   __asm      /* prolog */  
      {  
      push   ebp  
      mov      ebp, esp  
      sub      esp, __LOCAL_SIZE  
      }  
  
   /* Function body */  
  
   __asm      /* epilog */  
      {  
      mov      esp, ebp  
      pop      ebp  
      ret  
      }  
}     
```  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [naked 関数](../c-language/naked-functions.md)