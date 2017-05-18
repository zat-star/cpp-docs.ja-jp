---
title: "コンパイラ エラー C3539 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3539
dev_langs:
- C++
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f7e9f8d260d17d7561077aabb0dfc26bf20f8c07
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3539"></a>コンパイラ エラー C3539
'type': テンプレート引数は 'auto' を含む型をすることはできません  
  
 指定されたテンプレート引数の型は、使用量を含めることはできません、`auto`キーワードです。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  使用するテンプレート引数を指定して、`auto`キーワードです。  
  
## <a name="example"></a>例  
 次の例では、C3539 を生成します。  
  
```  
// C3539.cpp  
// Compile with /Zc:auto  
template<class T> class C{};  
int main()  
{  
   C<auto> c;   // C3539  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [auto キーワード](../../cpp/auto-keyword.md)
