---
title: "コンパイラの警告 (レベル 1) C4382 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4382
dev_langs:
- C++
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 4571fe618b0ae89251d2748fbbcdfcb654201054
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4382"></a>コンパイラの警告 (レベル 1) C4382
'type' をスローします _ _clrcall デストラクターまたはコピー コンス トラクターを持つ型 (/clr の) しかキャッチできません: 純粋なモジュール。  
  
 **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で使用されなくなりました。  
  
 コンパイルされたときに**/clr** (いない**/clr: 純粋な**)、例外処理メンバー関数を必要とするネイティブ型[_ _cdecl](../../cpp/cdecl.md)および not [_ _clrcall](../../cpp/clrcall.md)します。 ネイティブ型を使用してメンバー関数と`__clrcall`でコンパイルされたモジュールの呼び出し規約をキャッチできません**/clr**します。  
  
 コンパイルされたモジュールで、例外がキャッチされるかどうかは**/clr: 純粋な**、この警告を無視することができます。  
  
 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C4382 を生成します。  
  
```  
// C4382.cpp  
// compile with: /clr /W1 /c  
struct S {  
   __clrcall ~S() {}  
};  
  
struct T {  
   ~T() {}  
};  
  
int main() {  
   S s;  
   throw s;   // C4382  
  
   S * ps = &s;  
   throw ps;   // OK  
  
   T t;  
   throw t;   // OK  
}  
```
