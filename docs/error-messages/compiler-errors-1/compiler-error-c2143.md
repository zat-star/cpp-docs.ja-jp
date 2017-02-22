---
title: "コンパイラ エラー C2143 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2143"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2143"
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# コンパイラ エラー C2143
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

構文エラー : 'token1' が 'token2' の前にありません。  
  
 予測していたトークン \(つまり、空白以外の言語要素\) ではないトークンが検出されました。  
  
 このエラーの詳細については、"関数 try ブロックを使用する際に発生すると、参照してください [サポート技術情報の文書 241706](http://support.microsoft.com/kb/241706)。  
  
 「[C\+\+ Language Reference](../../cpp/cpp-language-reference.md)」を参照してコードが構文的に正しいかどうかを確認してください。  このエラーは発生した場所よりも後の行で生成されることがあるため、エラー発生行から何行か上のコードも調べてください。  
  
 C2143 エラーは別の状況でも発生します。  
  
 これは、この例に示すように、名前 \(`::`、`->`と `.`\) を修飾する演算子が `template`キーワードを指定する必要があるときに発生する:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143  
    {  
    };  
};  
  
```  
  
 `Ty::PutFuncType` がテンプレートではない場合既定で、C\+\+ がある、; したがって、次の `<` は不等号として解釈されます。正しく山かっこを解析できるように `PutFuncType` がテンプレートであることをコンパイラに明示的に指示する必要があります。  このエラーを解決するには、次に示すように依存する型の名前の `template` キーワードを使用する:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct  
    {  
    };  
};  
  
```  
  
 C2143 は **\/clr** が使用され、`using` のディレクティブに構文エラーがあるときに発生する:  
  
```cpp  
// C2143a.cpp  
// compile with: /clr /c  
using namespace System.Reflection;   // C2143  
using namespace System::Reflection;  
```  
  
 また、**\/clr**を使用したりせずに CLR 構文を使用してソース ファイルをコンパイルするときに発生する:  
  
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
  
 `if` のステートメントの直後の空白以外の文字は左かっこである必要があります。  それ以外の場合は、コンパイラで翻訳できません。  
  
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
  
 C2143 は \(}\)、右かっこ、またはセミコロンがエラーが 1 行の一つで、上で検出された行でないと発生する:  
  
```caml  
// C2143d.cpp  
// compile with: /c  
class X {  
   int member1;  
   int member2   // C2143  
} x;  
```  
  
 またはクラス宣言に無効なタグがある場合:  
  
```cpp  
// C2143e.cpp  
class X {  
   int member;  
} x;  
  
class + {};   // C2143 + is an invalid tag name  
class ValidName {};   // OK  
```  
  
 またはラベルがステートメントから切断されている場合。  ラベルだけを置く必要がある場合 \(複合ステートメントの最後にラベルを置く場合など\) は、null ステートメントを使ってください。  
  
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
  
 エラーは、不適切な呼び出しは標準 C\+\+ ライブラリの型に対して行われた場合に発生することがあります:  
  
```cpp  
// C2143g.cpp  
// compile with: /EHsc /c  
#include <vector>  
static vector<char> bad;   // C2143  
static std::vector<char> good;   // OK  
```  
  
 または `typename` missing キーワードがあります。:  
  
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
  
 または明示的なインスタンス化を定義しようとする:  
  
```cpp  
// C2143i.cpp  
// compile with: /EHsc /c  
// template definition  
template <class T>  
void PrintType(T i, T j) {}  
  
template void PrintType(float i, float j){}   // C2143  
template void PrintType(float i, float j);   // OK  
```  
  
 C プログラムでは、変数は関数の冒頭で宣言する必要があります。関数で宣言以外の命令を実行した後に、変数を宣言することはできません。  
  
```c  
// C2143j.c  
int main()   
{  
    int i = 0;  
    i++;  
    int j = 0; // C2143  
}  
  
```