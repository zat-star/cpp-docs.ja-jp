---
title: "__uuidof 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__LIBID_"
  - "__LIBID_cpp"
  - "__uuidof"
  - "__uuidof_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__LIBID_ キーワード [C++]"
  - "__uuidof キーワード [C++]"
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# __uuidof 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 式にアタッチされている GUID を取得します。  
  
## 構文  
  
```  
  
      __uuidof (  
   expression   
)  
```  
  
## 解説  
 *式*は、その型の型名、ポインター、参照、または配列、それらの型に特化したテンプレート、またはそれらの型の変数にすることができます。  引数は、アタッチされた GUID を見つけるためにコンパイラが使用できる限り有効です。  
  
 この組み込みの特殊なケースは、引数として **0** または **NULL** が指定される場合です。  この場合、`__uuidof` はゼロで構成された GUID を返します。  
  
 このキーワードを使用すると、次のものにアタッチされている GUID を抽出できます。  
  
-   [uuid](../cpp/uuid-cpp.md) 拡張属性によるオブジェクト。  
  
-   [module](../windows/module-cpp.md) 属性で作成されたライブラリ ブロック。  
  
> [!NOTE]
>  デバッグ ビルドでは、`__uuidof` は常にオブジェクトを動的に \(実行時に\) 初期化します。  リリース ビルドでは、`__uuidof` は静的に \(コンパイル時に\) オブジェクトを初期化できます。  
  
## 使用例  
 次のコード \(ole32.lib でコンパイル\) は、module 属性で作成されたライブラリ ブロックの uuid を表示します。  
  
```  
// expre_uuidof.cpp  
// compile with: ole32.lib  
#include "stdio.h"  
#include "windows.h"  
  
[emitidl];  
[module(name="MyLib")];  
[export]  
struct stuff {  
   int i;  
};  
  
int main() {  
   LPOLESTR lpolestr;  
   StringFromCLSID(__uuidof(MyLib), &lpolestr);  
   wprintf_s(L"%s", lpolestr);  
   CoTaskMemFree(lpolestr);  
}  
```  
  
## コメント  
 ライブラリ名がスコープ内でなくなった場合は、`__uuidof` の代わりに \_\_LIBID\_ を使用できます。  次に例を示します。  
  
```  
StringFromCLSID(__LIBID_, &lpolestr);  
```  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [単項演算子を含む式](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)