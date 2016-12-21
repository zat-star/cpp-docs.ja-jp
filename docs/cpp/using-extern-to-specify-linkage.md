---
title: "extern を使用したリンケージの指定 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "extern"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "宣言, 外部"
  - "extern キーワード [C++], C++ 以外の関数へのリンケージ"
  - "外部リンケージ, extern 修飾子"
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# extern を使用したリンケージの指定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
        extern string-literal { declaration-list }  
extern string-literal declaration  
```  
  
## 解説  
 `extern` キーワードは、変数または関数を宣言し、それが外部リンケージを持つことを指定します \(その名前は、それが定義されたファイル以外のファイルから見ることができます\)。  変数を変更するとき、`extern` は変数が静的存続期間を持つことを指定します \(プログラムの開始時に割り当てられ、プログラムの終了時に解放されます\)。  変数または関数は、別のソース ファイルで定義されることも、後で同じファイル内で定義されることもあります。  ファイル スコープでの変数と関数の宣言は既定で external です。  
  
## 使用例  
  
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
  
 C\+\+ では、文字列を使用する場合、`extern` により、別の言語のリンケージ規則が宣言に使用されることが示されます。  C の関数とデータには、C リンケージを持つと以前に宣言されている場合にのみ、アクセスできます。  ただし、別にコンパイルされた翻訳単位で定義する必要があります。  
  
 Microsoft C\+\+ は **string\-literal** フィールドで文字列 **"C"** と *"C\+\+"* をサポートします。  すべての標準の include ファイルは、`extern` "C" 構文を使用して、ランタイム ライブラリ関数が C\+\+ プログラムで使用されるようにします。  
  
## 使用例  
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
  
 関数に複数のリンケージ指定子がある場合、それらは一致する必要があります。関数を C と C\+\+ 両方のリンケージを持つ関数として宣言するとエラーになります。  また、プログラム内に、リンケージ指定子を含む関数宣言と含まない関数宣言がある場合、リンケージ指定子を含む宣言を最初に記述する必要があります。  既にリンケージ指定を持つ関数の冗長な宣言には、最初の宣言で指定したリンケージが与えられます。  例:  
  
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
  
 複合リンケージ指定子 \(**{ }**\) の本体内で **static** として明示的に宣言された関数およびオブジェクトは、静的関数またはオブジェクトとして扱われます。リンケージ指定子は無視されます。  `extern` キーワードを使用して宣言したかのように、他の関数やオブジェクトが動作します。  [extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md) キーワードの詳細については、「`extern`」を参照してください。  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\)Linkage Specifications](http://msdn.microsoft.com/ja-jp/d2b0cff1-7798-4c38-9ac8-61c3bfe2bfb9)   
 [extern ストレージ クラス指定子](../c-language/extern-storage-class-specifier.md)   
 [識別子の動作](../c-language/behavior-of-identifiers.md)   
 [リンケージ](../c-language/linkage.md)