---
title: "static_assert | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "C2338"
  - "static_assert_cpp"
  - "static_assert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アサーション [C++], static_assert"
  - "C++ のキーワード, static_assert"
  - "C2338"
  - "static_assert"
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# static_assert
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンパイル時にソフトウェアのアサーションをテストします。  指定された定数式が `false` の場合、コンパイラには、指定されたメッセージが表示され、コンパイルはエラー C2338 で失敗します。それ以外の場合、宣言は無効です。  
  
## 構文  
  
```  
static_assert(   
    constant-expression,   
    string-literal   
);  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`constant-expression`|ブール型に変換できる整数定数式。<br /><br /> 評価された式がゼロ \(false\) の場合、`string-literal` パラメーターが表示され、コンパイルはエラーで失敗します。  条件がゼロ以外 \(true\) の場合、`static_assert` 宣言は無効です。|  
|`string-literal`|`constant-expression` パラメーターがゼロの場合に表示するメッセージ。  メッセージは、コンパイラの[基本文字セット](../c-language/ascii-character-set.md)の文字列です。つまり、[マルチバイトまたはワイド文字](../Topic/Multibyte%20and%20Wide%20Characters.md)ではありません。|  
  
## 解説  
 `static_assert` 宣言の `constant-expression` パラメーターは、*ソフトウェアのアサーション*を表します。  ソフトウェアのアサーションは、プログラムの特定位置にある true となるはずの条件を指定します。  条件が true の場合、`static_assert` 宣言は無効です。  条件が false の場合、アサーションは失敗し、コンパイラは `string-literal` パラメーターのメッセージを表示し、コンパイルはエラーで失敗します。  
  
 `static_assert` 宣言は、コンパイル時にソフトウェアのアサーションをテストします。  これに対し、[assert マクロ、\_assert、\_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) マクロは実行時にソフトウェアのアサーションをテストするので、実行時に領域または時間の消費量が増えることになります。  `static_assert` 宣言は、テンプレート引数を `constant-expression` パラメーターに含めることができるため、テンプレートをデバッグする場合に特に便利です。  
  
 コンパイラは、宣言を検出すると、`static_assert` 宣言をチェックして構文エラーを探します。  テンプレート パラメーターに依存しない場合、コンパイラは `constant-expression` パラメーターを直ちに評価します。  それ以外の場合、テンプレートがインスタンス化されるときに、コンパイラは `constant-expression` パラメーターを評価します。  その結果、コンパイラは、宣言を検出したときに一度、テンプレートがインスタンス化されたときに再度、診断メッセージを発行することがあります。  
  
 `static_assert` キーワードは、名前空間、クラス、またはブロック スコープで使用できます。 `static_assert` キーワードは、名前空間スコープで使用できるため、プログラムに新しい名前を組み込むことはありませんが、技術的には宣言です。  
  
## 説明  
 次の例では、`static_assert` 宣言は名前空間スコープを持ちます。  コンパイラは `void *` 型のサイズがわかっているので、式は直ちに評価されます。  
  
## 例  
  
```  
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");  
```  
  
## 説明  
 次の例では、`static_assert` 宣言はクラス スコープを持ちます。  `static_assert` は、テンプレート パラメーターが *plain old data* \(POD\) 型であることを検証します。  コンパイラは `static_assert` が宣言されている場合はそれをチェックしますが、`basic_string` クラス テンプレートが `main()` でインスタンス化されるまで `constant-expression` パラメーターを評価しません。  
  
## 例  
  
```  
#include <type_traits>  
#include <iosfwd>  
namespace std {  
template <class CharT, class Traits = std::char_traits<CharT> >  
class basic_string {  
    static_assert(tr1::is_pod<CharT>::value,  
                  "Template argument CharT must be a POD type in class template basic_string");  
    // ...  
    };  
}  
struct NonPOD {  
    NonPOD(const NonPOD &) {}  
    virtual ~NonPOD() {}  
};  
int main()  
{  
    std::basic_string<char> bs;  
}  
```  
  
## 説明  
 次の例では、`static_assert` 宣言はブロック スコープを持ちます。  `static_assert` は、VMPage 構造体のサイズがシステムの仮想メモリ pagesize と等しいことを検証します。  
  
## 例  
  
```  
#include <sys/param.h> // defines PAGESIZE  
class VMMClient {  
public:  
    struct VMPage { // ...   
           };  
    int check_pagesize() {  
    static_assert(sizeof(VMPage) == PAGESIZE,  
        "Struct VMPage must be the same size as a system virtual memory page.");  
    // ...  
    }  
// ...  
};  
```  
  
## 参照  
 [アサーションとユーザー指定のメッセージ \(C\+\+\)](../cpp/assertion-and-user-supplied-messages-cpp.md)   
 [\#error ディレクティブ](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert マクロ、\_assert、\_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [テンプレート](../Topic/Templates%20\(C++\).md)   
 [ASCII 文字セット](../c-language/ascii-character-set.md)   
 [宣言](../misc/declarations.md)