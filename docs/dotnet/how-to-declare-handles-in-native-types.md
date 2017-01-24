---
title: "方法: ネイティブ型のハンドルを宣言する | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "gcroot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gcroot キーワード [C++]"
  - "ハンドル, 宣言"
  - "型 [C++], 宣言 (ハンドルを)"
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: ネイティブ型のハンドルを宣言する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ネイティブ型のハンドルの型を宣言することはできません。vcclr.h には C\+\+ ヒープから CLR オブジェクトを参照するためのタイプ セーフなラッパー テンプレート `gcroot` を提供します。  このテンプレートでは、仮想ハンドルをネイティブ型に埋め込み、それを基になる型のように取り扱います。  ほとんどの場合は、`gcroot` オブジェクトを埋め込み型としてキャストなしに使用できます。  ただし、[for each、in](../dotnet/for-each-in.md) では、基になるマネージ参照を取得するためには `static_cast` を使用する必要があります。  
  
 `gcroot` テンプレートは、System::Runtime::InteropServices::GCHandle 値クラスの機能を使用して実装されます。これは、ガベージ コレクションされるヒープを識別する "ハンドル" を提供します。  ハンドル自身はガベージ コレクションされず、不要になると `gcroot` クラスのデストラクター \(このデストラクターは手動で呼び出すことはできません\) によって解放されます。  `gcroot` オブジェクトをネイティブ ヒープにインスタンス化する場合、そのリソースに delete を呼び出す必要があります。  
  
 ランタイムは、ハンドルと参照する CLR オブジェクトとの間の関連付けを維持します。  ガベージ コレクションされたヒープで CLR オブジェクトが移動された場合、ハンドルはオブジェクトの新しいアドレスを返します。  `gcroot` テンプレートに割り当てる前に、変数を固定しておく必要はありません。  
  
## 使用例  
 次の例は、ネイティブ スタックに `gcroot` オブジェクトを作成する方法を示します。  
  
```  
// mcpp_gcroot.cpp  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
class CppClass {  
public:  
   gcroot<String^> str;   // can use str as if it were String^  
   CppClass() {}  
};  
  
int main() {  
   CppClass c;  
   c.str = gcnew String("hello");  
   Console::WriteLine( c.str );   // no cast required  
}  
```  
  
  **hello**   
## 使用例  
 次の例は、ネイティブ ヒープに `gcroot` オブジェクトを作成する方法を示します。  
  
```  
// mcpp_gcroot_2.cpp  
// compile with: /clr  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
struct CppClass {  
   gcroot<String ^> * str;  
   CppClass() : str(new gcroot<String ^>) {}  
  
   ~CppClass() { delete str; }  
  
};  
  
int main() {  
   CppClass c;  
   *c.str = gcnew String("hello");  
   Console::WriteLine( *c.str );  
}  
```  
  
  **hello**   
## 使用例  
 次の例は、ボックス化された型の `gcroot` を使用して、`gcroot` でネイティブ型の値型 \(参照型ではなく\) への参照を保持する方法を示します。  
  
```  
// mcpp_gcroot_3.cpp  
// compile with: /clr  
#include < vcclr.h >  
using namespace System;  
  
public value struct V {  
   String^ str;  
};  
  
class Native {  
public:  
   gcroot< V^ > v_handle;  
};  
  
int main() {  
   Native native;  
   V v;  
   native.v_handle = v;  
   native.v_handle->str = "Hello";  
   Console::WriteLine("String in V: {0}", native.v_handle->str);  
}  
```  
  
  **String in V: Hello**   
## 参照  
 [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)