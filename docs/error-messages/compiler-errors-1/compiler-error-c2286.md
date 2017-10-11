---
title: "コンパイラ エラー C2286 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2286
dev_langs:
- C++
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e1fca7ee629c35c083f6852a914e2ab62b4d5590
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2286"></a>コンパイラ エラー C2286
'identifier' の形式のメンバーへのポインターは、既に '継承の' 宣言は無視に設定します。  
  
 クラスには、次の 2 つの異なるメンバーへのポインター表現が存在します。  
  
 詳細については、次を参照してください。[継承キーワード](../../cpp/inheritance-keywords.md)です。  
  
## <a name="example"></a>例  
 次の例では C2286 が生成されます。  
  
```  
// C2286.cpp  
// compile with: /c  
class __single_inheritance X;  
class __multiple_inheritance X;   // C2286  
class  __multiple_inheritance Y;   // OK  
```
