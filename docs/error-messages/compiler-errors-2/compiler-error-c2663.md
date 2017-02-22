---
title: "コンパイラ エラー C2663 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2663"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2663"
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2663
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : number オーバーロードに 'this' ポインターのための必要な定義がされていません。  
  
 `this` ポインターを、オーバーロードされたメンバー関数に変換できませんでした。  
  
 このエラーは、`const` 以外のメンバー関数が `const` オブジェクトから呼び出されたことが原因で発生する場合があります。解決方法は次のとおりです。  
  
1.  オブジェクト宣言から `const` を削除します。  
  
2.  オーバーロードするメンバー関数に `const` を追加します。  
  
 次の例では警告 C2663 が生成されます。  
  
```  
// C2663.cpp  
struct C {  
   void f() volatile {}  
   void f() {}  
};  
  
struct D {  
   void f() volatile;  
   void f() const {}  
};  
  
const C *pcc;  
const D *pcd;  
  
int main() {  
   pcc->f();    // C2663  
   pcd->f();    // OK  
}  
```