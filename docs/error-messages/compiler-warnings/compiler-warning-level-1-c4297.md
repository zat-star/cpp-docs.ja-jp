---
title: "コンパイラの警告 (レベル 1) C4297 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4297
dev_langs:
- C++
helpviewer_keywords:
- C4297
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c21453d185fed2c33e7cb054e77e1698fadf491b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4297"></a>コンパイラの警告 (レベル 1) C4297
'function': 例外をスローしないはずだがそれをする関数。  
  
 関数宣言が含まれていますが、(場合によって暗黙的)`noexcept`指定子、空`throw`例外指定子または[無視されます。](../../cpp/nothrow-cpp.md)属性、および定義は&1; つ以上[スロー](../../cpp/try-throw-and-catch-statements-cpp.md)ステートメントです。 C4297 を解決するには、`__declspec(nothrow)`、`noexcept(true)`、または `throw()` を使用して宣言した関数で例外をスローしようとしないでください。 または、`noexcept`、`throw()`、`__declspec(nothrow)` の指定を削除します。  
  
 既定では、コンパイラは、ユーザー定義のデストラクターとデアロケーターの関数およびコンパイラによって生成される特殊なメンバー関数用に、暗黙的な `noexcept(true)` 指定子を生成します。 これは、ISO C++11 標準に準拠します。 暗黙的な noexcept 指定子が生成されないようにし、コンパイラは Visual Studio 2013 の非標準動作を元に戻す、使用、 **/Zc:implicitNoexcept-**コンパイラ オプション。 詳細については、次を参照してください。 [/Zc:implicitNoexcept (暗黙の型の例外指定子)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md)します。  
  
 例外の指定の詳細については、次を参照してください。[例外の仕様 (スロー)](../../cpp/exception-specifications-throw-cpp.md)します。 参照してください[/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)コンパイル時の例外処理動作を変更する方法の詳細。  
  
 この警告は _ _declspec に対しても生成 ([dllexport](../../cpp/dllexport-dllimport.md)) 関数が C++ の関数がある場合でも、extern"C"をマークします。  
  
 次の例では C4297 が生成されます。  
  
```  
// C4297.cpp  
// compile with: /W1 /LD  
void __declspec(nothrow) f1()   // declared nothrow  
// try the following line instead  
// void f1()  
{  
   throw 1;   // C4297  
}  
```
