---
title: "novtable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "novtable"
  - "novtable_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++], novtable"
  - "novtable __declspec キーワード"
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# novtable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 これは `__declspec` 拡張属性です。  
  
 この形式の `__declspec` は任意のクラス宣言に適用できますが、純粋なインターフェイス クラス \(それ自体はインスタンス化されないクラス\) だけに適用してください。  `__declspec` は、クラスのコンストラクターおよびデストラクター内の vfptr を初期化するコードをコンパイラが生成することを阻止します。  多くの場合、これは、クラスに関連付けられている vtable への参照のみを削除するので、リンカーはこれを削除します。  この形式の `__declspec` を使用すると、コード サイズが大幅に削減されます。  
  
 `novtable` でマークされたクラスをインスタンス化してから、クラス メンバーにアクセスしようとすると、アクセス違反 \(AV\) となります。  
  
## 使用例  
  
```  
// novtable.cpp  
#include <stdio.h>  
  
struct __declspec(novtable) X {  
   virtual void mf();  
};  
  
struct Y : public X {  
   void mf() {  
      printf_s("In Y\n");  
   }  
};  
  
int main() {  
   // X *pX = new X();  
   // pX->mf();   // Causes a runtime access violation.  
  
   Y *pY = new Y();  
   pY->mf();  
}  
```  
  
  **In Y**   
## END Microsoft 固有の仕様  
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)