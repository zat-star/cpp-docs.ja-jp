---
title: "コンパイラ エラー C3530 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3530
dev_langs:
- C++
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
caps.latest.revision: 5
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
ms.openlocfilehash: ddaa07e0c06a871815f42c4f5d6760befdb06b30
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3530"></a>コンパイラ エラー C3530
'auto' を他の型指定子と組み合わせることはできません  
  
 型指定子を併用、`auto`キーワードです。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  使用する変数の宣言で型指定子を使用しないでください、`auto`キーワードです。  
  
## <a name="example"></a>例  
 次の例では C3530 のため変数`x`が両方と宣言されている、`auto`キーワードと型`int`、例をコンパイルしたので、 **/Zc:auto**します。  
  
```  
// C3530.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto int x;   // C3530  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [auto キーワード](../../cpp/auto-keyword.md)
