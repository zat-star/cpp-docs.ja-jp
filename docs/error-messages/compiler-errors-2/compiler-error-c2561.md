---
title: "コンパイラ エラー C2561 | Microsoft Docs"
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
  - "C2561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2561"
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 関数が値を戻すように宣言されていますが、関数定義に 'return' ステートメントがありません。  
  
 関数は値を返すように宣言されていますが、関数定義に `return` ステートメントがありません。  
  
 このエラーは、不正な関数プロトタイプが原因で発生する場合があります。  
  
1.  関数が値を返さないときは、戻り値の型 [void](../../cpp/void-cpp.md) で関数を宣言します。  
  
2.  関数のすべての分岐の戻り値が、プロトタイプで宣言されていることを確認します。  
  
3.  `AX` レジスタに戻り値を格納するようなインライン アセンブリ ルーチンを持つ C\+\+ 関数は、return ステートメントが必要な場合もあります。  `AX` 内の値をテンポラリ変数にコピーし、関数からはこの変数を返すようにします。  
  
 次の例では警告 C2561 が生成されます。  
  
```  
// C2561.cpp  
int Test(int x) {  
   if (x) {  
      return;   // C2561  
      // try the following line instead  
      // return 1;  
   }  
   return 0;  
}  
  
int main() {  
   Test(1);  
}  
```