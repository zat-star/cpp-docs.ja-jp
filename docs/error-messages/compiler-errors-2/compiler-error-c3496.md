---
title: "コンパイラ エラー C3496 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3496
dev_langs:
- C++
helpviewer_keywords:
- C3496
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 72013d9345361bfbf0ee1dedecb27402850520c8
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3496"></a>コンパイラ エラー C3496
'this' は常に値によってキャプチャされます。'&' は無視されました  
  
 参照で `this` ポインターをキャプチャすることはできません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   値で `this` ポインターをキャプチャします。  
  
## <a name="example"></a>例  
 次の例では、 `this` ポインターへの参照がラムダ式のキャプチャ リストにあるため、C3496 が生成されます。  
  
```  
// C3496.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      [&this] {}(); // C3496  
   }  
};  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
