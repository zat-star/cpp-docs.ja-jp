---
title: "コンパイラ エラー C2362 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2362"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2362"
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2362
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' の初期化が 'goto label' によって行われませんでした。  
  
 [\/Za](../../build/reference/za-ze-disable-language-extensions.md) を指定してコンパイルした場合は、ラベルにジャンプすることによって、識別子が初期化されなくなります。  
  
 初期化子を含む宣言は、実行されない閉じたブロック内でその宣言が行われている場合や変数が既に初期化されている場合を除いてスキップできません。  
  
 次の例では警告 C2326 が生成されます。  
  
```  
// C2362.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   int i = 1;      // C2362, initialization skipped  
label1:;  
}  
```  
  
 解決方法 :  
  
```  
// C2362b.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   {  
      int j = 1;   // OK, this block is never entered  
   }  
label1:;  
}  
```