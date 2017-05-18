---
title: "コンパイラ エラー C3490 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3490
dev_langs:
- C++
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 83a215b1c4883ba7ed4b285af8c4efafe2cfaa05
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="compiler-error-c3490"></a>コンパイラ エラー C3490
'var' は const オブジェクトを通じてアクセスされているため変更できません  
  
 `const` メソッドで宣言されているラムダ式は、変更不能なメンバー データを変更することはできません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   メソッド宣言から `const` 修飾子を削除します。  
  
## <a name="example"></a>例  
 次の例は、メンバー変数を変更するため、C3490 が生成されます`_i`で、`const`メソッド。  
  
```  
// C3490a.cpp  
// compile with: /c  
  
class C  
{  
   void f() const   
   {  
      auto x = [=]() { _i = 20; }; // C3490  
   }  
  
   int _i;  
};  
```  
  
## <a name="example"></a>例  
 次の例では、メソッド宣言から `const` 修飾子を削除して C3490 を解決します。  
  
```  
// C3490b.cpp  
// compile with: /c  
  
class C  
{  
   void f()  
   {  
      auto x = [=]() { _i = 20; };  
   }  
  
   int _i;  
};  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
