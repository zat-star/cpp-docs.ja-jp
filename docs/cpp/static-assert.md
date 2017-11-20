---
title: "static_assert |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: static_assert_cpp
dev_langs: C++
helpviewer_keywords:
- C++ keywords, static_assert
- C2338
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9073f513000684fd75ccdba250c2f92513a94bdc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="staticassert"></a>static_assert
コンパイル時にソフトウェアのアサーションをテストします。 指定された定数式が場合`false`が提供されている場合、コンパイラが、指定したメッセージを表示され、コンパイル エラー C2338 で失敗はそれ以外の場合、宣言には効果はありません。  
  
## <a name="syntax"></a>構文  
  
```   
static_assert( constant-expression, string-literal );  

**Visual Studio 2017 and later:**
static_assert( constant-expression ); 
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`constant-expression`|ブール型に変換できる整数定数式。<br /><br /> 評価された式がゼロ (false) の場合、`string-literal` パラメーターが表示され、コンパイルはエラーで失敗します。 条件がゼロ以外 (true) の場合、`static_assert` 宣言は無効です。|  
|`string-literal`|`constant-expression` パラメーターがゼロの場合に表示するメッセージ。 メッセージが内の文字の文字列、[基本文字セット](../c-language/ascii-character-set.md); は、コンパイラのではなく、[マルチバイトまたはワイド文字](../c-language/multibyte-and-wide-characters.md)です。|  
  
## <a name="remarks"></a>コメント  
 `constant-expression`のパラメーター、`static_assert`宣言を表します、*ソフトウェアのアサーション*です。 ソフトウェアのアサーションは、プログラムの特定位置にある true となるはずの条件を指定します。 条件が true の場合、`static_assert` 宣言は無効です。 条件が false の場合、アサーションは失敗し、コンパイラは `string-literal` パラメーターのメッセージを表示し、コンパイルはエラーで失敗します。 Visual Studio 2017 以降では、文字列リテラル パラメーターは省略できます。 
  
 `static_assert` 宣言は、コンパイル時にソフトウェアのアサーションをテストします。 これに対し、 [assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)マクロは、実行時にソフトウェアのアサーションをテストし、領域または時間で実行時のコストが生じます。 `static_assert` 宣言は、テンプレート引数を `constant-expression` パラメーターに含めることができるため、テンプレートをデバッグする場合に特に便利です。  
  
 コンパイラは、宣言を検出すると、`static_assert` 宣言をチェックして構文エラーを探します。 テンプレート パラメーターに依存しない場合、コンパイラは `constant-expression` パラメーターを直ちに評価します。 それ以外の場合、テンプレートがインスタンス化されるときに、コンパイラは `constant-expression` パラメーターを評価します。 その結果、コンパイラは、宣言を検出したときに一度、テンプレートがインスタンス化されたときに再度、診断メッセージを発行することがあります。  
  
 `static_assert` キーワードは、名前空間、クラス、またはブロック スコープで使用できます。 `static_assert` キーワードは、名前空間スコープで使用できるため、プログラムに新しい名前を組み込むことはありませんが、技術的には宣言です。  
  
## <a name="description"></a>説明  
 次の例では、`static_assert` 宣言は名前空間スコープを持ちます。 コンパイラは `void *` 型のサイズがわかっているので、式は直ちに評価されます。  
  
## <a name="example"></a>例  
  
```  
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");  
```  
  
## <a name="description"></a>説明  
 次の例では、`static_assert` 宣言はクラス スコープを持ちます。 `static_assert`テンプレート パラメーターがあることを確認、*プレーンな古いデータ*(POD) 型です。 コンパイラは `static_assert` が宣言されている場合はそれをチェックしますが、`constant-expression` クラス テンプレートが `basic_string` でインスタンス化されるまで `main()` パラメーターを評価しません。  
  
## <a name="example"></a>例  
  
```  
#include <type_traits>  
#include <iosfwd>  
namespace std {  
template <class CharT, class Traits = std::char_traits<CharT> >  
class basic_string {  
    static_assert(std::is_pod<CharT>::value,  
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
  
## <a name="description"></a>説明  
 次の例では、`static_assert` 宣言はブロック スコープを持ちます。 `static_assert` は、VMPage 構造体のサイズがシステムの仮想メモリ pagesize と等しいことを検証します。  
  
## <a name="example"></a>例  
  
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
  
## <a name="see-also"></a>関連項目  
 [アサーションとユーザー指定のメッセージ (C++)](../cpp/assertion-and-user-supplied-messages-cpp.md)   
 [#error ディレクティブ (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [テンプレート](../cpp/templates-cpp.md)   
 [ASCII 文字セット](../c-language/ascii-character-set.md)   
 [宣言と定義](declarations-and-definitions-cpp.md)