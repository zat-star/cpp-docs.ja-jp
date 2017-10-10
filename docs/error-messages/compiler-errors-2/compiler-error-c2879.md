---
title: "コンパイラ エラー C2879 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2879
dev_langs:
- C++
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4bb972ffa8bee016dd158490d123353bd6f46a8e
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2879"></a>コンパイラ エラー C2879
'symbol': 既存の名前空間を指定できます代替名名前空間のエイリアス定義によってのみ  
  
 作成することはできません、[名前空間の別名](../../cpp/namespaces-cpp.md#namespace_aliases)名前空間以外のシンボルにします。  
  
 次の例では、C2879 が生成されます。  
  
```  
// C2879.cpp  
int main() {  
   int i;  
   namespace A = i;   // C2879 i is not a namespace  
}  
```
