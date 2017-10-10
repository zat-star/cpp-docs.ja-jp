---
title: "コンパイラ エラー C2883 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2883
dev_langs:
- C++
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 28c2031c3e659099507a8e59758e27f364dd29b9
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2883"></a>コンパイラ エラー C2883
'name': 関数宣言が 'identifier' を使用して宣言によって導入されると競合しています  
  
 関数を複数回定義しようとするとします。 最初の定義が、名前空間から行われた、`using`宣言します。 2 つ目は、ローカルの定義をでした。  
  
 次の例では、C2883 が生成されます。  
  
```  
// C2883.cpp  
namespace A {  
   void z(int);  
}  
  
int main() {  
   using A::z;  
   void z(int);   // C2883  z is already defined  
}  
```
