---
title: "コンパイラ エラー C3482 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b19769a8a326613401263fa7700b85c36a9dbbe1
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

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
