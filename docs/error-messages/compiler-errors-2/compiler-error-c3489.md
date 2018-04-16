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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b4a0115bbb6d00a4e83d0ae3343b1af1b8024002
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)