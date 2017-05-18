---
title: "コンパイラ エラー C2143 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2143
dev_langs:
- C++
helpviewer_keywords:
- C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
caps.latest.revision: 23
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: faa9361da0091ec86628af19a03eadb133ea43cc
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2143"></a>コンパイラ エラー C2143
構文エラー: 'token2' の前に ' token1' がありません  
  
 コンパイラでは、トークン (空白以外の言語要素) を推測され、代わりにトークンが検出されました。  
  
 このエラーについては関数 try ブロックを使用している場合を参照してください[サポート技術情報記事 241706](http://support.microsoft.com/kb/241706)します。  
  
 チェック、 [C++ 言語リファレンス](../../cpp/cpp-language-reference.md)コードが正しい構文を確認します。 コンパイラは、問題が発生する行を検出した後、このエラーをレポート可能性があります、するため、エラーの前にいくつかの行のコードを確認してください。  
  
 C2143 は、さまざまな状況で発生することができます。  
  
 名前に限定できる演算子が発生することができます (`::`、 `->`、および`.`) キーワードを使用して実行する必要があります`template`この例のように。  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143  
    {  
    };  
};  
  
```  
  
 C++ では既定では、想定される`Ty::PutFuncType`; テンプレートではありません、次にそのため、`<`は小として解釈されます-不等号します。  必要がありますコンパイラに通知する明示的にいる`PutFuncType`テンプレートは、山かっこでは正しく解析できるようにします。 このエラーを修正するには、`template`依存する型の名前を次に示すように、キーワード。  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct  
    {  
    };  
};  
  
```  
  
 C2143 エラーが発生する可能性がときに**/clr**を使用し、`using`ディレクティブは、構文エラー。  
  
```cpp  
// C2143a.cpp  
// compile with: /clr /c  
using namespace System.Reflection;   // C2143  
using namespace System::Reflection;  
```  
  
 使用せず、CLR の構文を使用してソース コード ファイルをコンパイルするときにも発生**/clr**:  
  
```cpp  
// C2143b.cpp  
ref struct A {   // C2143 error compile with /clr  
   void Test() {}  
};  
  
int main() {  
   A a;  
   a.Test();  
}  
```  
  
 これに続く最初の空白以外の文字、`if`ステートメントは、左かっこをする必要があります。 コンパイラは、その他を変換できません。  
  
```cpp  
// C2143c.cpp  
int main() {  
   int j = 0;  
  
   // OK  
   if (j < 25)  
      ;  
  
   if (j < 25)   // C2143  
}  
```  
  
 C2143 右中かっこ、かっこ、またはセミコロンが、エラーが検出された行に不足している場合に発生したり、行の&1; つ上の真上します。  
  
```cpp  
// C2143d.cpp  
// compile with: /c  
class X {  
   int member1;  
   int member2   // C2143  
} x;  
```  
  
 または、クラス宣言に無効なタグが存在する場合。  
  
```cpp  
// C2143e.cpp  
class X {  
   int member;  
} x;  
  
class + {};   // C2143 + is an invalid tag name  
class ValidName {};   // OK  
```  
  
 または、ラベルがステートメントにアタッチされていない場合。 場合単独でラベルを配置する必要がありますなどの複合ステートメントの最後にアタッチして null ステートメントにします。  
  
```cpp  
// C2143f.cpp  
// compile with: /c  
void func1() {  
   // OK  
   end1:  
      ;  
  
   end2:   // C2143  
}  
```  
  
 エラーは、C++ 標準ライブラリ内の型を修飾されていない呼び出しが行われたときに発生します。  
  
```cpp  
// C2143g.cpp  
// compile with: /EHsc /c  
#include <vector>  
static vector<char> bad;   // C2143  
static std::vector<char> good;   // OK  
```  
  
 指定または`typename`キーワード。  
  
```cpp  
// C2143h.cpp  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
template <typename T>  
X<T>::Y X<T>::memFunc() {   // C2143  
// try the following line instead  
// typename X<T>::Y X<T>::memFunc() {  
   return Y();  
}  
```  
  
 明示的なインスタンス化を定義しようとする場合、または。  
  
```cpp  
// C2143i.cpp  
// compile with: /EHsc /c  
// template definition  
template <class T>  
void PrintType(T i, T j) {}  
  
template void PrintType(float i, float j){}   // C2143  
template void PrintType(float i, float j);   // OK  
```  
  
 C プログラムでは、関数の先頭にある変数を宣言する必要があり、関数が非宣言命令を実行した後にこれらを宣言することはできません。  
  
```C  
// C2143j.c  
int main()   
{  
    int i = 0;  
    i++;  
    int j = 0; // C2143  
}  
```  

