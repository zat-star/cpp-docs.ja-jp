---
title: "コンパイラ エラー C3480 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3480
dev_langs:
- C++
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d84314d20ea00e880981e418c2b5b11008f74229
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3480"></a>コンパイラ エラー C3480
'var': ラムダ キャプチャ変数は、外側の関数スコープの変数である必要があります  
  
 ラムダ キャプチャ変数が外側の関数スコープの変数ではありません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   ラムダ式のキャプチャ リストから変数を削除します。  
  
## <a name="example"></a>例  
 変数 `global` が外側の関数スコープではないため、次の例では C3480 が生成されます。  
  
```  
// C3480a.cpp  
  
int global = 0;  
int main()  
{  
   [&global] { global = 5; }(); // C3480  
}  
```  
  
## <a name="example"></a>例  
 次の例では、ラムダ式のキャプチャ リストから変数 `global` を削除することによって C3480 を解決しています。  
  
```  
// C3480b.cpp  
  
int global = 0;  
int main()  
{  
   [] { global = 5; }();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
