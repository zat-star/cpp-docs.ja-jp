---
title: "コンパイラ エラー C3255 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3255
dev_langs: C++
helpviewer_keywords: C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6be3f8c7e699d7bc8514e1e4f66905473780b961
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3255"></a>コンパイラ エラー C3255
'値の型': ネイティブ ヒープでこの値型のオブジェクトを動的に割り当てることはできません  
  
 値型のインスタンス (を参照してください[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)) マネージ メンバーが含まれているスタックではなく、ヒープを作成できます。  
  
 次の例では、C3255 が生成されます。  
  
```  
// C3255.cpp  
// compile with: /clr  
using namespace System;  
value struct V {  
   Object^ o;  
};  
  
value struct V2 {  
   int i;  
};  
  
int main() {  
   V* pv = new V;   // C3255  
   V2* pv2 = new V2;  
   V v2;  
}  
```  
