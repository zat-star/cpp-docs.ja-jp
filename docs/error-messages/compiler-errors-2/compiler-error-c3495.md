---
title: "コンパイラ エラー C3495 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3495
dev_langs: C++
helpviewer_keywords: C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8cf93a5de639ce0c8270ef374eabdedb6c6551bd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3495"></a>コンパイラ エラー C3495
'var': ラムダ キャプチャには自動ストレージ存続期間が指定されている必要があります  
  
 `static` または `extern`とマークされている変数など、自動ストレージ存続期間がない変数をキャプチャすることはできません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   `static` または `extern` 変数をラムダ式のキャプチャ リストに渡さないでください。  
  
## <a name="example"></a>例  
 次の例では、 `static` 変数 `n` がラムダ式のキャプチャ リストにあるため、C3495 が生成されます。  
  
```  
// C3495.cpp  
  
int main()  
{  
   static int n = 66;  
   [&n]() { return n; }(); // C3495  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)   


