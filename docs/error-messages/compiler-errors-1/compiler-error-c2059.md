---
title: "コンパイラ エラー C2059 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2059
dev_langs:
- C++
helpviewer_keywords:
- C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 47be5c5ad1d10933d1d4fcf81d2aa549c23b4e9e
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2059"></a>コンパイラ エラー C2059
構文エラー: 'トークン'  
  
 トークンには、構文エラーが発生しました。  
  
 次の例は、エラーを宣言する行のエラー メッセージを生成`j`します。  
  
```  
// C2059e.cpp  
// compile with: /c  
// C2143 expected  
// Error caused by the incorrect use of '*'.  
   int j*; // C2059   
```  
  
 エラーの原因を判断するには、エラー メッセージに記載されている行だけでなく、その上に行を調べます。 行を調べて、問題に関する手がかりとしないである場合は、エラー メッセージに記載されている行とその上におそらく複数行をコメント アウトしてください。  
  
 直後に続くシンボルのエラー メッセージが発生したかどうか、`typedef`変数、ソース コードで、変数が定義されていることを確認します。  
  
 シンボルと評価された場合、何も発生する可能性がする c2059 ことがありますと**/D** `symbol` ** = **をコンパイルするために使用します。  
  
```  
// C2059a.cpp  
// compile with: /DTEST=  
#include <stdio.h>  
  
int main() {  
   #ifdef TEST  
      printf_s("\nTEST defined %d", TEST);   // C2059  
   #else  
      printf_s("\nTEST not defined");  
   #endif  
}  
```  
  
 C2059 エラーが発生することが別のケースは、構造体を関数の既定の引数で指定するアプリケーションをコンパイルする場合です。 引数の既定値には、式を指定する必要があります。 初期化子リスト — たとえば、1 つ構造体を初期化するために使用 — 式ではありません。  この問題を解決するのには、必要な初期化を実行するコンス トラクターを定義します。  
  
 次の例では、C2059 が生成されます。  
  
```  
// C2059b.cpp  
// compile with: /c  
struct ag_type {  
   int a;  
   float b;  
   // Uncomment the following line to resolve.  
   // ag_type(int aa, float bb) : a(aa), b(bb) {}   
};  
  
void func(ag_type arg = {5, 7.0});   // C2059  
void func(ag_type arg = ag_type(5, 7.0));   // OK  
```  
  
 メンバーのテンプレート クラスまたはクラスの外側の関数を定義する場合は、C2059 も取得できます。 詳細については、次を参照してください。[サポート技術情報記事 241949](http://support.microsoft.com/kb/241949)します。  
  
 C2059 で不正な形式はキャストが発生します。  
  
 次の例では、C2059 が生成されます。  
  
```  
// C2059c.cpp  
// compile with: /clr  
using namespace System;  
ref class From {};  
ref class To : public From {};  
  
int main() {  
   From^ refbase = gcnew To();  
   To^ refTo = safe_cast<To^>(From^);   // C2059  
   To^ refTo2 = safe_cast<To^>(refbase);   // OK  
}  
```  
  
 C2059 は、ピリオドを含む名前空間の名前を作成しようとする場合にも発生します。  
  
 次の例では、C2059 が生成されます。  
  
```  
// C2059d.cpp  
// compile with: /c  
namespace A.B {}   // C2059  
  
// OK  
namespace A  {  
   namespace B {}  
}  
```  
  
 C2059 はオペレーター名を修飾するときに発生する可能性が (`::`、 `->`、および`.`)、キーワードの後に`template`この例のように。  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::Rebind<X>::Other AX; // error C2059  
};  
  
```  
  
 C++ では既定では、想定される`AY::Rebind`; テンプレートではありません、次にそのため、`<`は小として解釈されます-不等号します。  必要がありますコンパイラに通知する明示的にいる`Rebind`テンプレートは、山かっこでは正しく解析できるようにします。 このエラーを修正するには、`template`依存する型の名前を次に示すように、キーワード。  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::template Rebind<X>::Other AX; // correct  
};  
  
```
