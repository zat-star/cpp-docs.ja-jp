---
title: "コンパイラ エラー C3533 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3533
dev_langs:
- C++
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
caps.latest.revision: 6
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 73a9efca8245d4d83e8e9cda05c54a502607ea51
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3533"></a>コンパイラ エラー C3533
'type': パラメーターを 'auto' を含む型を持つことはできません  
  
 メソッドまたはテンプレートのパラメーターを宣言することはできません、`auto`キーワード場合、既定[/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md)コンパイラ オプションは有効にします。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  削除、`auto`パラメーター宣言からのキーワードです。  
  
## <a name="example"></a>例  
 持つ関数パラメーターを宣言しているために、次の例で c3535 が発生、`auto`キーワードとそれをコンパイルした**/Zc:auto**します。  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j){} // C3533  
```  
  
## <a name="example"></a>例  
 持つテンプレート パラメーターを宣言しているために、次の例で c3535 が発生、`auto`キーワードとそれをコンパイルした**/Zc:auto**します。  
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C{}; // C3533  
```  
  
## <a name="see-also"></a>関連項目  
 [auto キーワード](../../cpp/auto-keyword.md)   
 [/Zc:auto (変数型の推測)](../../build/reference/zc-auto-deduce-variable-type.md)
