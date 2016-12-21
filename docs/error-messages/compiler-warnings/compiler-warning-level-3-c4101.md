---
title: "コンパイラの警告 (レベル 3) C4101 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4101"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4101"
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 3) C4101
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : ローカル変数は 1 度も使われていません。  
  
 ローカル変数が一度も使用されていません。  この警告は、次のような明らかな状況で発生します。  
  
```  
// C4101a.cpp  
// compile with: /W3  
int main() {  
int i;   // C4101  
}  
```  
  
 ただし、クラスのインスタンスを通じて **static** なメンバー関数を呼び出す場合にも発生します。  
  
```  
// C4101b.cpp  
// compile with:  /W3  
struct S {  
   static int func()  
   {  
      return 1;  
   }  
};  
  
int main() {  
   S si;   // C4101, si is never used  
   int y = si.func();  
   return y;  
}  
```  
  
 ここでは、コンパイラは `si` に関する情報を使用して **static** 関数にアクセスしますが、**static** 関数の呼び出しにはクラスのインスタンスが不要であるため、この警告が発生します。  この警告を解決するには、次の方法があります。  
  
-   コンストラクターを追加し、コンパイラがコンストラクター内で `func` の呼び出しに `si` のインスタンスを使用するようにします。  
  
-   `func` の定義から **static** キーワードを削除します。  
  
-   `int y = S::func();` のように、**static** 関数を明示的に呼び出します。