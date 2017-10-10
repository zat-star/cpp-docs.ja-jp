---
title: "コンパイラ エラー C2663 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2663
dev_langs:
- C++
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a9efe20b4a80b9ff6f337d32acd35320125008dc
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2663"></a>コンパイラ エラー C2663
'function': 'this' ポインターの有効な変換がある番号のオーバー ロードがありません  
  
 コンパイラは変換できませんでした`this`メンバー関数のオーバー ロードされたバージョンのいずれかにします。  
  
 このエラーは、以外を呼び出すことによって発生することができます`const`メンバー関数を`const`オブジェクト。  考えられる解決策:  
  
1.  削除、`const`オブジェクトの宣言からです。  
  
2.  追加`const`メンバー関数のオーバー ロードのいずれかにします。  
  
 次の例では、C2663 が生成されます。  
  
```  
// C2663.cpp  
struct C {  
   void f() volatile {}  
   void f() {}  
};  
  
struct D {  
   void f() volatile;  
   void f() const {}  
};  
  
const C *pcc;  
const D *pcd;  
  
int main() {  
   pcc->f();    // C2663  
   pcd->f();    // OK  
}  
```
