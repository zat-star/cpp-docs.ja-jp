---
title: "コンパイラ エラー C3255 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3255
dev_langs:
- C++
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 2739be65060cabd5e40fb0156c44aca23f0b7dcc
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3255"></a>コンパイラ エラー C3255
'値型': ネイティブ ヒープにこの値型のオブジェクトを動的に割り当てることはできません  
  
 値型のインスタンス (を参照してください[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)) マネージ メンバーが含まれているスタックではなく、ヒープを作成できます。  
  
 次の例では、c3255 エラーが生成されます。  
  
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

