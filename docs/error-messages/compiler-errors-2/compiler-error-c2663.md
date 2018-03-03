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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a9c0ded6888855528867ec7993bcc28eac8045c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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