---
title: "コンパイラ エラー C2750 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2750
dev_langs:
- C++
helpviewer_keywords:
- C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96f66115c2e51a7ed49cc20c6b5da94a61cab555
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2750"></a>コンパイラ エラー C2750
'type': 参照型で 'new' は使用できません'gcnew' を代わりに使用します。  
  
 ガベージ コレクション ヒープ上に配置するインスタンスが発生した場合、CLR の型のインスタンスを作成する必要がありますを使用して[gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md)です。  
  
 次の例では、C2750 が生成されます。  
  
```  
// C2750.cpp  
// compile with: /clr  
ref struct Y1 {};  
  
int main() {  
   Y1 ^ x = new Y1;   // C2750  
  
   // try the following line instead  
   Y1 ^ x2 = gcnew Y1;  
}  
```