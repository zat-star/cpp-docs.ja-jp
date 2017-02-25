---
title: "リンカ ツール エラー LNK2020 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2020"
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# リンカ ツール エラー LNK2020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

未解決のトークン 'token'  
  
 未定義の外部エラーと同様ですが、参照はメタデータを経由しています。  メタデータには、すべての関数とデータが定義されている必要があります。  
  
 このエラーを解決するには、次のどちらかの操作を実行します。  
  
-   欠けている関数またはデータを定義します。  
  
-   欠けている関数またはデータが既に定義されているオブジェクト ファイルあるいはライブラリを取り込みます。  
  
## 使用例  
 次の例では LNK2020 エラーが生成されます。  
  
```  
// LNK2020.cpp  
// compile with: /clr /LD  
ref struct A {  
   A(int x);   // LNK2020  
   static int f();   // LNK2020  
};  
  
// OK  
ref struct B {  
   B(int x) {}  
   static int f() { return 0; }  
};  
```  
  
## 使用例  
 LNK2020 は、マネージ テンプレート型の変数を作成し、その型をインスタンス化しない場合にも発生します。  
  
 次の例では LNK2020 エラーが生成されます。  
  
```  
// LNK2020_b.cpp  
// compile with: /clr   
  
template <typename T>  
ref struct Base {  
   virtual void f1() {};  
};  
  
template <typename T>  
ref struct Base2 {  
   virtual void f1() {};  
};  
  
int main() {  
   Base<int>^ p;   // LNK2020  
   Base2<int>^ p2 = gcnew Base2<int>();   // OK  
};  
```