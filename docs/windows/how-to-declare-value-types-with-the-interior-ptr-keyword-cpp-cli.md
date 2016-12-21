---
title: "How to: Declare Value Types with the interior_ptr Keyword (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ptr keyword"
  - "value types, declaring"
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Declare Value Types with the interior_ptr Keyword (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`interior_ptr` は値型で使用できます。  
  
> [!IMPORTANT]
>  この言語機能は **\/clr** コンパイラ オプションによって、**\/ZW** コンパイラ オプションによってサポートされます。  
  
## 例  
  
### 説明  
 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] の次のサンプルでは、値型の `interior_ptr` を使用する方法を示します。  
  
### コード  
  
```  
// interior_ptr_value_types.cpp  
// compile with: /clr  
value struct V {  
   V(int i) : data(i){}  
   int data;  
};  
  
int main() {  
   V v(1);  
   System::Console::WriteLine(v.data);  
  
   // pointing to a value type  
   interior_ptr<V> pv = &v;  
   pv->data = 2;  
  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
  
   // pointing into a value type  
   interior_ptr<int> pi = &v.data;  
   *pi = 3;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
}  
```  
  
### 出力  
  
```  
1  
2  
2  
3  
3  
3  
```  
  
## 例  
  
### 説明  
 値型には、`this` のポインターは interior\_ptr に評価されます。  
  
 値型 `V`の非静的なメンバー関数本体で、`this` は値が関数が呼び出されるオブジェクトのアドレスの型 `interior_ptr<V>` の式です。  
  
### コード  
  
```  
// interior_ptr_value_types_this.cpp  
// compile with: /clr /LD  
value struct V {  
   int data;  
   void f() {  
      interior_ptr<V> pv1 = this;  
      // V* pv2 = this;   error  
   }  
};  
```  
  
## 例  
  
### 説明  
 次の例は、静的メンバーを持つアドレス演算子を使用する方法を示します。  
  
 静的な Visual C\+\+ 型メンバーのアドレスをネイティブ ポインターについて説明します。静的な値型のメンバーのアドレスは、値型のメンバーがランタイム ヒープに割り当てられ、ガベージ コレクターによって移動できるため、マネージ ポインターです。  
  
### コード  
  
```  
// interior_ptr_value_static.cpp  
// compile with: /clr  
using namespace System;  
value struct V { int i; };  
  
ref struct G {  
   static V v = {22};   
   static int i = 23;   
   static String^ pS = "hello";   
};  
  
int main() {  
   interior_ptr<int> p1 = &G::v.i;  
   Console::WriteLine(*p1);  
  
   interior_ptr<int> p2 = &G::i;  
   Console::WriteLine(*p2);  
  
   interior_ptr<String^> p3 = &G::pS;  
   Console::WriteLine(*p3);  
}  
```  
  
### 出力  
  
```  
22  
23  
hello  
```  
  
## 参照  
 [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)