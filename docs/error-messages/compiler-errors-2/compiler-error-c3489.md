---
title: "コンパイラ エラー C3489 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3489
dev_langs:
- C++
helpviewer_keywords:
- C3489
ms.assetid: 47b58d69-459d-4499-abc7-5f0b9303d773
caps.latest.revision: 8
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
ms.openlocfilehash: dd21e87beb83169e9ee827ad36903ac61d624ae3
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3489"></a>コンパイラ エラー C3489
既定のキャプチャ モードが値キャプチャである場合、'var' が必要です  
  
 ラムダ式の既定のキャプチャ モードが値渡しであることを指定する場合は、その式の capture 句に値によって変数を渡すことができません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   capture 句に明示的に変数を渡さないでください。  
  
-   既定のキャプチャ モードとして値渡しを指定しないでください。  
  
-   既定のキャプチャ モードとして参照渡しを指定します。  
  
-   capture 句に参照によって変数を渡します。 (これにより、ラムダ式の動作が変更される可能性があります。)  
  
## <a name="example"></a>例  
 次の例では、既定のモードが値渡しであるラムダ式の capture 句に、変数 `n` が値渡しで出現し、C3489 が生成されます。  
  
```  
// C3489a.cpp  
  
int main()  
{  
   int n = 5;  
   [=, n]() { return n; } (); // C3489  
}  
```  
  
## <a name="example"></a>例  
 次の例では、C3489 について考えられる 4 つの解決策を示します。  
  
```  
// C3489b.cpp  
  
int main()  
{  
   int n = 5;  
  
   // Possible resolution 1:  
   // Do not explicitly pass n to the capture clause.  
   [=]() { return n; } ();  
  
   // Possible resolution 2:  
   // Do not specify by-value as the default capture mode.  
   [n]() { return n; } ();  
  
   // Possible resolution 3:  
   // Specify by-reference as the default capture mode.  
   [&, n]() { return n; } ();  
  
   // Possible resolution 4:  
   // Pass n by reference to the capture clause.  
   [&n]() { return n; } ();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
