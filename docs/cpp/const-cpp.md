---
title: "const (C++) | Microsoft Docs"
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
  - "const_cpp"
  - "const"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const キーワード [C++]"
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# const (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

データ宣言を修飾するとき、**const** キーワードはオブジェクトまたは変数が変更できないことを指定します。  
  
## 構文  
  
```  
  
        const declaration ;  
member-function const ;  
```  
  
## const の値  
 **const** キーワードは、変数の値が定数であることを指定し、プログラマによる変更を防止するようにコンパイラに指示します。  
  
```  
// constant_values1.cpp  
int main() {  
   const int i = 5;  
   i = 10;   // C3892  
   i++;   // C2105  
}  
```  
  
 C\+\+ では、**\#define** プリプロセッサ ディレクティブの代わりに [const](../preprocessor/hash-define-directive-c-cpp.md) キーワードを使用して定数値を定義できます。  **const** で定義されている値は型チェックの対象になり、定数式の代わりに使用できます。  C\+\+ では、次のように **const** 変数で配列のサイズを指定できます。  
  
```  
// constant_values2.cpp  
// compile with: /c  
const int maxarray = 255;  
char store_char[maxarray];  // allowed in C++; not allowed in C  
```  
  
 C では、定数値は既定で外部リンケージに設定されるため、ソース ファイルでのみ指定できます。  C\+\+ では、定数値は既定で内部リンケージに設定されるため、ヘッダー ファイルで指定できます。  
  
 **const** キーワードは、ポインター宣言でも使用できます。  
  
```  
// constant_values3.cpp  
int main() {  
   char *mybuf = 0, *yourbuf;  
   char *const aptr = mybuf;  
   *aptr = 'a';   // OK  
   aptr = yourbuf;   // C3892  
}  
```  
  
 **const** として宣言されている変数へのポインターは、**const** として宣言されたポインターにのみ割り当てることができます。  
  
```  
// constant_values4.cpp  
#include <stdio.h>  
int main() {  
   const char *mybuf = "test";  
   char *yourbuf = "test2";  
   printf_s("%s\n", mybuf);  
  
   const char *bptr = mybuf;   // Pointer to constant data  
   printf_s("%s\n", bptr);  
  
   // *bptr = 'a';   // Error  
}  
```  
  
 定数データへのポインターを関数パラメーターとして使用して、ポインターを通じて渡されるパラメーターが関数によって変更されないようにすることができます。  
  
 **const** として宣言されたオブジェクトの場合、[定数メンバー関数](../misc/constant-member-functions.md)のみ呼び出すことができます。  これによって、定数オブジェクトは変更されなくなります。  
  
```  
birthday.getMonth();    // Okay  
birthday.setMonth( 4 ); // Error  
```  
  
 非定数オブジェクトに対して、定数または非定数のメンバー関数を呼び出すことができます。  また、**const** キーワードを使用してメンバー関数をオーバーロードすることもできます。これによって、定数および非定数オブジェクトに対して関数の異なるバージョンが呼び出されるようになります。  
  
 **const** キーワードを持つコンストラクターまたはデストラクターは宣言できません。  
  
## const のメンバー関数  
 **const** キーワードを指定してメンバー関数を宣言すると、その関数は呼び出したオブジェクトを変更しない "読み取り専用" 関数であると指定されます。  定数メンバー関数は、非静的データ メンバーを変更したり、定数でないメンバー関数を呼び出すことはできません。定数メンバー関数を宣言するには、引数リストの閉じかっこの後に **const** キーワードを追加します。  **const** キーワードは、宣言と定義の両方で必要になります。  
  
```  
// constant_member_function.cpp  
class Date  
{  
public:  
   Date( int mn, int dy, int yr );  
   int getMonth() const;     // A read-only function  
   void setMonth( int mn );   // A write function; can't be const  
private:  
   int month;  
};  
  
int Date::getMonth() const  
{  
   return month;        // Doesn't modify anything  
}  
void Date::setMonth( int mn )  
{  
   month = mn;          // Modifies data member  
}  
int main()  
{  
   Date MyDate( 7, 4, 1998 );  
   const Date BirthDate( 1, 18, 1953 );  
   MyDate.setMonth( 4 );    // Okay  
   BirthDate.getMonth();    // Okay  
   BirthDate.setMonth( 4 ); // C2662 Error  
}  
```  
  
## C と C\+\+ での const の相違点  
 C ソース コード ファイルで変数を **const** として宣言する場合は、次のようにします。  
  
```  
const int i = 2;  
```  
  
 そして、次のように、この変数を別のモジュールで使用できます。  
  
```  
extern const int i;  
```  
  
 しかし、C\+\+ で同じ動作を得るには、次のように **const** 変数を宣言する必要があります。  
  
```  
extern const int i = 2;  
```  
  
 C ソース コード ファイルで使用できるように C\+\+ ソース コード ファイルで `extern` 変数を宣言する場合は、次のコードを使用してください。  
  
```  
extern "C" const int x=10;  
```  
  
 C\+\+ コンパイラによる名前修飾を防止します。  
  
## 解説  
 メンバー関数のパラメーター リストの後に続く場合、**const** キーワードは関数が呼び出しの対象であるオブジェクトを変更しないことを指定します。  
  
 **const** の詳細については、次のトピックを参照してください。  
  
-   [定数値](../misc/constant-values.md)  
  
-   [定数メンバー関数](../misc/constant-member-functions.md)  
  
-   [const ポインターと volatile ポインター](../Topic/const%20and%20volatile%20Pointers.md)  
  
-   [型修飾子 \(C 言語リファレンス\)](../c-language/type-qualifiers.md)  
  
-   [volatile](../cpp/volatile-cpp.md)  
  
-   [\#define](../preprocessor/hash-define-directive-c-cpp.md)  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)