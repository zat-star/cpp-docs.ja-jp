---
title: "Microsoft C/C++ の拡張機能 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "! 演算子, 拡張機能 (C++ の)"
  - "!= 演算子"
  - "& 演算子, 拡張機能 (C/C++ の)"
  - "&& 演算子"
  - "&= 演算子"
  - "^ 演算子, 拡張機能 (C/C++ の)"
  - "^= 演算子, C++ の拡張機能"
  - "| 演算子, 拡張"
  - "|| 演算子"
  - "|= 演算子"
  - "~ 演算子, 拡張機能 (C/C++ の)"
  - "And 演算子, 拡張機能 (C/C++ の)"
  - "and_eq 演算子"
  - "compl メソッド"
  - "拡張"
  - "拡張, C 言語"
  - "iso646.h ヘッダー"
  - "Microsoft C/C++ の拡張機能"
  - "NOT 演算子"
  - "not_eq 演算子"
  - "Or 演算子, Microsoft C/C++ の拡張機能"
  - "or_eq 演算子"
  - "Visual C, Microsoft 拡張機能"
  - "Visual C++, 拡張機能 (C/C++ の)"
  - "Xor 演算子, Microsoft C/C++ の拡張機能"
  - "xor_eq 演算子"
ms.assetid: e811a74a-45ba-4c00-b206-2f2321b8689a
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Microsoft C/C++ の拡張機能
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ は、ANSI C および ANSI C\+\+ 標準を次のように拡張します。  
  
## キーワード  
 複数のキーワードが追加されます。  「[C\+\+ キーワード](../../cpp/keywords-cpp.md)」の一覧で、先頭に 2 つのアンダースコアがあるキーワードは Visual C\+\+ の拡張機能です。  
  
## 静的な定数型の整数 \(または列挙\) メンバーのクラス外定義  
 標準 \(**\/Za**\) では、以下に示すように、データ メンバーのクラス外定義が必要です。  
  
```  
class CMyClass  {  
   static const int max = 5;  
   int m_array[max];  
}  
...  
const int CMyClass::max;   // out of class definition  
```  
  
 **\/Ze** では、静的で定数型の整数および列挙のデータ メンバーのクラス外定義は省略可能です。  クラス内に初期化子を持つことができるのは、静的で定数型の整数と列挙だけです。初期化式には、定数型の式を使用する必要があります。  
  
 クラス外定義がヘッダー ファイルに指定され、そのヘッダー ファイルを複数のソース ファイルでインクルードする場合は、エラーを防ぐために [selectany](../../cpp/selectany.md) を使用します。  たとえば、次のようになります。  
  
```  
__declspec(selectany) const int CMyClass::max = 5;  
```  
  
## キャスト  
 C\+\+ コンパイラおよび C コンパイラは、次の種類の非 ANSI キャストをサポートします。  
  
-   左辺値を生成するための非 ANSI キャスト。  たとえば、次のようになります。  
  
    ```  
    char *p;  
    (( int * ) p )++;  
    ```  
  
    > [!NOTE]
    >  この拡張機能は、C 言語でのみ使用できます。  C\+\+ コードで次の ANSI C 標準形式を使用して、ポインターを別の型へのポインターであるかのように変更できます。  
  
     この例を次のように書き換えると、ANSI C 規格に準拠します。  
  
    ```  
    p = ( char * )(( int * )p + 1 );  
    ```  
  
-   関数ポインターからデータ ポインターへの非 ANSI キャスト。  たとえば、次のようになります。  
  
    ```  
    int ( * pfunc ) ();   
    int *pdata;  
    pdata = ( int * ) pfunc;  
    ```  
  
     上の例と同じキャストを行い、ANSI 規格に準拠させるには、次に示すように関数ポインターをまず `uintptr_t` 型にキャストし、その後データ ポインターにキャストします。  
  
    ```  
    pdata = ( int * ) (uintptr_t) pfunc;  
    ```  
  
## 可変長の引数リスト  
 C\+\+ および C コンパイラでは、可変個の引数を指定する関数宣言子を使用できます。その後ろには、型を指定する関数定義を記述します。  
  
```  
void myfunc( int x, ... );  
void myfunc( int x, char * c )  
{ }  
```  
  
## 単一行コメント  
 C コンパイラでは、次のように 2 つのスラッシュ \(\/\/\) で始まる単一行コメントがサポートされています。  
  
```  
// This is a single-line comment.  
```  
  
## スコープ  
 C コンパイラでは、次のようなスコープ関連のコードを記述できます。  
  
-   extern を static として再定義する。  
  
    ```  
    extern int clip();  
    static int clip()  
    {}  
    ```  
  
-   同じスコープ内で typedef 定義を複数回記述する。  
  
    ```  
    typedef int INT;  
    typedef int INT;  
    ```  
  
-   関数宣言子をファイル スコープにする。  
  
    ```  
    void func1()  
    {  
        extern int func2( double );  
    }  
    int main( void )  
    {  
        func2( 4 );    //  /Ze passes 4 as type double  
    }                  //  /Za passes 4 as type int  
    ```  
  
-   非定数式で初期化したブロック スコープ変数を使用する。  
  
    ```  
    int clip( int );  
    int bar( int );  
    int main( void )  
    {  
        int array[2] = { clip( 2 ), bar( 4 ) };  
    }  
    int clip( int x )  
    {  
        return x;  
    }  
    int bar( int x )  
    {  
        return x;  
    }  
    ```  
  
## データの宣言と定義  
 C コンパイラでは、以下のデータ宣言およびデータ定義の機能をサポートしています。  
  
-   初期化子内に文字定数と文字列定数を混在させる。  
  
    ```  
    char arr[5] = {'a', 'b', "cde"};  
    ```  
  
-   ビット フィールドを **unsigned int** や **signed int** 以外のベース型で指定する。  
  
-   型がない宣言子:  
  
    ```  
    x;  
    int main( void )  
    {  
        x = 1;  
    }  
    ```  
  
-   可変長配列を構造体および共用体の最後のフィールドとして指定する。  
  
    ```  
    struct zero  
    {  
        char *c;  
        int zarray[];  
    };  
    ```  
  
-   名前のない \(無名\) 構造体を使用する。  
  
    ```  
    struct  
    {  
        int i;  
        char *s;  
    };  
    ```  
  
-   名前のない \(無名\) 共用体を使用する。  
  
    ```  
    union  
    {  
        int i;  
        float fl;  
    };  
    ```  
  
-   名前のないメンバーを使用する。  
  
    ```  
    struct s  
    {  
       unsigned int flag : 1;  
       unsigned int : 31;  
    }  
    ```  
  
## 浮動小数点組み込み型の関数  
 C\+\+ および C コンパイラは、**x86 固有の仕様→\>**`atan`、`atan2`、`cos`、`exp`、`log`、`log10`、`sin`、`sqrt`、`tan` の各関数の**←x86 固有の仕様**インライン生成をサポートします \(**\/Oi** が指定されている場合\)。  C コンパイラの場合、これらの組み込みでは `errno` 変数が設定されないため、ANSI に準拠しなくなります。  
  
## const ポインター パラメーターの参照を予測している関数に非 const ポインター パラメーターを渡す  
 これは C\+\+ の拡張機能です。  このコードは **\/Ze** でコンパイルされます。  
  
```  
typedef   int   T;  
  
const T  acT = 9;      // A constant of type 'T'  
const T* pcT = &acT;   // A pointer to a constant of type 'T'  
  
void func2 ( const T*& rpcT )   // A reference to a pointer to a constant of type 'T'  
{  
   rpcT = pcT;  
}  
  
T*   pT;               // A pointer to a 'T'  
  
void func ()  
{  
   func2 ( pT );      // Should be an error, but isn't detected  
   *pT   = 7;         // Invalidly overwrites the constant 'acT'  
}  
```  
  
## ISO646.H が有効でない  
 **\/Ze** で次の演算子の表示形式を使用する場合は、iso646.h をインクルードする必要があります。  
  
-   && \(and\)  
  
-   &\= \(and\_eq\)  
  
-   & \(bitand\)  
  
-   &#124; \(bitor\)  
  
-   ~ \(compl\)  
  
-   \!\(not\)  
  
-   \!\= \(not\_eq\)  
  
-   &#124;&#124; \(or\)  
  
-   &#124;\= \(or\_eq\)  
  
-   ^ \(xor\)  
  
-   ^\= \(xor\_eq\)  
  
## リテラル文字列のアドレスの型が const char \(\*\) \[\] ではなく const char \[\] である  
 **\/Za** で char const \(\*\)\[4\] を出力し、**\/Ze** で char const \[4\] を出力する例を次に示します。  
  
```  
#include <stdio.h>  
#include <typeinfo>  
  
int main()  
{  
    printf_s("%s\n", typeid(&"abc").name());  
}  
```  
  
## 参照  
 [\/Za、\/Ze \(言語拡張機能の無効化\)](../../build/reference/za-ze-disable-language-extensions.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)