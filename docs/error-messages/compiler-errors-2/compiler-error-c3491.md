---
title: "コンパイラ エラー C3491 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3491
dev_langs:
- C++
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
caps.latest.revision: 6
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
ms.openlocfilehash: c6087d7be6ac5fce959d7f54c529401d9b57631e
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3491"></a>コンパイラ エラー C3491
'var': 変更できないラムダでは値キャプチャは変更できません  
  
 変更できないラムダ式では、値によってキャプチャされる変数の値を変更できません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   `mutable` キーワードでラムダ式を宣言します。または、  
  
-   ラムダ式のキャプチャ リストへの参照によって変数を渡します。  
  
## <a name="example"></a>例  
 次の例では、変更できないラムダ式の本体がキャプチャ変数 `m`を変更するため、C3491 が生成されます。  
  
```  
// C3491a.cpp  
  
int main()  
{  
   int m = 55;  
   [m](int n) { m = n; }(99); // C3491  
}  
```  
  
## <a name="example"></a>例  
 次の例では、ラムダ式を `mutable` キーワードで宣言することで C3491 を解決しています。  
  
```  
// C3491b.cpp  
  
int main()  
{  
   int m = 55;  
   [m](int n) mutable { m = n; }(99);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
