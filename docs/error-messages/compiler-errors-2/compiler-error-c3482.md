---
title: "コンパイラ エラー C3482 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3482
dev_langs:
- C++
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: ca80df6224311db87c4c5f1425d825cbada2116c
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3482"></a>コンパイラ エラー C3482
'this' は非静的メンバー関数内でのラムダ キャプチャとしてのみ使用できます  
  
 静的メソッドまたはグローバル関数で宣言されているラムダ式のキャプチャ リストに `this` を渡すことはできません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   外側の関数を静的でないメソッドに変換します。または、  
  
-   ラムダ式のキャプチャ リストから `this` ポインターを削除します。  
  
## <a name="example"></a>例  
 次の例では、C3482 が生成されます。  
  
```  
// C3482.cpp  
// compile with: /c  
  
class C  
{  
public:  
   static void staticMethod()  
   {  
      [this] {}(); // C3482  
   }  
};  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
