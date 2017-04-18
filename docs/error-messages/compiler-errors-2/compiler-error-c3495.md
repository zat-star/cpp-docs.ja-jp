---
title: "コンパイラ エラー C3495 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3495
dev_langs:
- C++
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: d5eb9f62cb18d9d94f74caa8925dbba0ed453737
ms.lasthandoff: 04/12/2017

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
 [(NOTINBUILD)ストレージ クラス指定子](http://msdn.microsoft.com/en-us/10b3d22d-cb40-450b-994b-08cf9a211b6c)
