---
title: "Extern リンケージの指定を使用した |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: extern
dev_langs: C++
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db93feb8c8fad13cf8de082858e68b89f93b5323
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-extern-to-specify-linkage"></a>extern を使用したリンケージの指定
## <a name="syntax"></a>構文  
  
```  
  
      extern string-literal { declaration-list }  
extern string-literal declaration  
```  
  
## <a name="remarks"></a>コメント  
 `extern` キーワードは、変数または関数を宣言し、それが外部リンケージを持つことを指定します (その名前は、それが定義されたファイル以外のファイルから見ることができます)。 変数を変更するとき、`extern` は変数が静的存続期間を持つことを指定します (プログラムの開始時に割り当てられ、プログラムの終了時に解放されます)。 変数または関数は、別のソース ファイルで定義されることも、後で同じファイル内で定義されることもあります。 ファイル スコープでの変数と関数の宣言は既定で external です。  
  
## <a name="example"></a>例  
  
```  
// specifying_linkage1.cpp  
int i = 1;  
void other();  
  
int main() {  
   // Reference to i, defined above:  
   extern int i;  
}  
  
void other() {  
   // Address of global i assigned to pointer variable:  
   static int *external_i = &i;  
  
   // i will be redefined; global i no longer visible:  
   // int i = 16;  
}  
```  
  
 C++ では、文字列を使用する場合、`extern` により、別の言語のリンケージ規則が宣言に使用されることが示されます。 C の関数とデータには、C リンケージを持つと以前に宣言されている場合にのみ、アクセスできます。 ただし、別にコンパイルされた翻訳単位で定義する必要があります。  
  
 Microsoft C は、文字列をサポートしている**"C"**と**"C++"**で、*文字列リテラル*フィールドです。 すべての標準の include ファイルは、`extern` "C" 構文を使用して、ランタイム ライブラリ関数が C++ プログラムで使用されるようにします。  
  
## <a name="example"></a>例  
 次の例では、C リンケージを持つ名前を宣言する別の方法を示します。  
  
```  
// specifying_linkage2.cpp  
// compile with: /c  
// Declare printf with C linkage.  
extern "C" int printf( const char *fmt, ... );  
  
//  Cause everything in the specified header files  
//   to have C linkage.  
extern "C" {  
   // add your #include statements here  
   #include <stdio.h>  
}  
  
//  Declare the two functions ShowChar and GetChar  
//   with C linkage.  
extern "C" {  
   char ShowChar( char ch );  
   char GetChar( void );  
}  
  
//  Define the two functions ShowChar and GetChar  
//   with C linkage.  
extern "C" char ShowChar( char ch ) {  
   putchar( ch );  
   return ch;  
}  
  
extern "C" char GetChar( void ) {  
   char ch;  
  
   ch = getchar();  
   return ch;  
}  
  
// Declare a global variable, errno, with C linkage.  
extern "C" int errno;  
```  
  
 関数に複数のリンケージ指定子がある場合、それらは一致する必要があります。関数を C と C++ 両方のリンケージを持つ関数として宣言するとエラーになります。 また、プログラム内に、リンケージ指定子を含む関数宣言と含まない関数宣言がある場合、リンケージ指定子を含む宣言を最初に記述する必要があります。 既にリンケージ指定を持つ関数の冗長な宣言には、最初の宣言で指定したリンケージが与えられます。 例:  
  
```  
extern "C" int CFunc1();  
...  
int CFunc1();            // Redeclaration is benign; C linkage is  
                         //  retained.  
  
int CFunc2();  
...  
extern "C" int CFunc2(); // Error: not the first declaration of  
                         //  CFunc2;  cannot contain linkage  
                         //  specifier.  
```  
  
 関数とオブジェクトが明示的に宣言**静的**複合リンケージ指定子の本体内で (**{}**) は静的関数またはオブジェクトとして扱われます、リンケージ指定子は無視されます。 `extern` キーワードを使用して宣言したかのように、他の関数やオブジェクトが動作します。 (を参照してください[extern リンケージの指定を使用した](../cpp/using-extern-to-specify-linkage.md)詳細については、`extern`キーワードです)。  
  
## <a name="see-also"></a>参照  
 [キーワード](../cpp/keywords-cpp.md)   
 [extern ストレージ クラス指定子](../c-language/extern-storage-class-specifier.md)   
 [識別子の動作](../c-language/behavior-of-identifiers.md)   
 [リンケージ](../c-language/linkage.md)