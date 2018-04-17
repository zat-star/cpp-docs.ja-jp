---
title: (C++) を非推奨 |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/28/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- deprecated_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce1d98917609af0eeb42c197cd55bb2179039fe0
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="deprecated-c"></a>deprecated (C++)
このトピックでは、Microsoft に固有の仕様について declspec 宣言使用されなくなりました。 C++ 14 に関する情報の`[[deprecated]]`属性、および Microsoft 固有の declspec またはプラグマとその属性を使用する場合のガイダンスを参照してください。 [C++ の標準属性](attributes.md)です。

 以下に示すような例外、**非推奨**宣言と同じ機能を提供する、[廃止](../preprocessor/deprecated-c-cpp.md)プラグマ。  
  
-   **廃止**宣言ことができます、非推奨として特定の形式の関数のオーバー ロードを指定する一方、プラグマ形式は、関数名のすべてのオーバー ロードされたフォームに適用されます。  
  
-   **廃止**宣言では、コンパイル時に表示されるメッセージを指定することができます。 このメッセージのテキストをマクロから取り込むことができます。  
  
-   マクロはで非推奨としてマークされているだけ、**廃止**プラグマ。  
  
 非推奨の識別子または標準の使用が見つかったかどうか[ `[[deprecated]]` ](attributes.md) 、属性、 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)警告がスローされます。  
  
## <a name="example"></a>例  
 次の例では、関数を非推奨としてマークする方法、および非推奨の関数が使用されている場合、コンパイル時に表示されるメッセージを指定する方法を示します。  
  
```  
// deprecated.cpp  
// compile with: /W3  
#define MY_TEXT "function is deprecated"  
void func1(void) {}  
__declspec(deprecated) void func1(int) {}  
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}  
__declspec(deprecated(MY_TEXT)) void func3(int) {}  
  
int main() {  
   func1();  
   func1(1);   // C4996  
   func2(1);   // C4996  
   func3(1);   // C4996  
}  
```  
  
## <a name="example"></a>例  
 次の例では、クラスを非推奨としてマークする方法、および非推奨のクラスが使用されている場合、コンパイル時に表示されるメッセージを指定する方法を示します。  
  
```  
// deprecate_class.cpp  
// compile with: /W3  
struct __declspec(deprecated) X {  
   void f(){}  
};  
  
struct __declspec(deprecated("** X2 is deprecated **")) X2 {  
   void f(){}  
};  
  
int main() {  
   X x;   // C4996  
   X2 x2;   // C4996  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [__declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)