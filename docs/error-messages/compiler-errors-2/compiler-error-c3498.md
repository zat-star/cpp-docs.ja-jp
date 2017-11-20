---
title: "コンパイラ エラー C3498 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3498
dev_langs: C++
helpviewer_keywords: C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0429b9d21829f772596b6d0fd2c51d72b0924e26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3498"></a>コンパイラ エラー C3498
'var': マネージが変数または WinRTtype をキャプチャすることはできません  
  
 ラムダで、マネージ型または Windows ランタイム型を持つ変数をキャプチャすることはできません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   マネージ変数または Windows ランタイム変数をラムダ式のパラメーター リストに渡します。  
  
## <a name="example"></a>例  
 次の例では、マネージ型を持つ変数がラムダ式のキャプチャ リストに表示されるため、C3498 が生成されます。  
  
```  
// C3498a.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [&s](String ^ r)   
      { return String::Concat(s, r); } (", World!"); // C3498  
}  
```  
  
## <a name="example"></a>例  
 次の例では、マネージ型の変数 `s` をラムダ式のパラメーター リストに渡すことにより、C3498 を解決します。  
  
```  
// C3498b.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [](String ^ s, String ^ r)   
      { return String::Concat(s, r); } (s, ", World!");  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)