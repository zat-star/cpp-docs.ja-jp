---
title: "naked 関数に関する規則と制限 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "naked 関数"
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# naked 関数に関する規則と制限
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 次の規則と制約が naked 関数に適用されます。  
  
-   `return` ステートメントは許可されていません。  
  
-   構造化例外処理コンストラクトと C\+\+ の例外処理コンストラクトは、スタック フレームを越えてアンワインドする必要があるため許可されていません。  
  
-   同じ理由で、`setjmp` の形式は禁止されています。  
  
-   `_alloca` 関数の使用は禁止されています。  
  
-   プロローグ シーケンスの前にローカル変数の初期化コードが出現しないように、初期化されたローカル変数は関数のスコープ内では許可されません。  特に、C\+\+ オブジェクトの宣言は関数のスコープでは許可されません。  ただし、入れ子になったスコープ内には初期化されたデータが含まれる場合があります。  
  
-   フレーム ポインター最適化 \(\/Oy コンパイラ オプション\) は推奨されていませんが、naked 関数に対しては自動的に抑制されます。  
  
-   関数の構文スコープでは C\+\+ クラス オブジェクトを宣言できません。  ただし、入れ子になったブロックではオブジェクトを宣言できます。  
  
-   `naked` キーワードは、[\/clr](../build/reference/clr-common-language-runtime-compilation.md) オプションでコンパイルするときは無視されます。  
  
-   [\_\_fastcall](../cpp/fastcall.md) naked 関数の場合、C\/C\+\+ コードにいずれかのレジスタ引数への参照があるときは常に、プロローグ コードはその変数のスタックの場所にそのレジスタの値を格納する必要があります。  次に例を示します。  
  
```  
// nkdfastcl.cpp  
// compile with: /c  
// processor: x86  
__declspec(naked) int __fastcall  power(int i, int j) {  
   // calculates i^j, assumes that j >= 0  
  
   // prolog  
   __asm {  
      push ebp  
      mov ebp, esp  
      sub esp, __LOCAL_SIZE  
     // store ECX and EDX into stack locations allocated for i and j  
     mov i, ecx  
     mov j, edx  
   }  
  
   {  
      int k = 1;   // return value  
      while (j-- > 0)   
         k *= i;  
      __asm {   
         mov eax, k   
      };  
   }  
  
   // epilog  
   __asm {  
      mov esp, ebp  
      pop ebp  
      ret  
   }  
}  
```  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [naked 関数呼び出し](../Topic/Naked%20Function%20Calls.md)