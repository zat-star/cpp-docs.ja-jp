---
title: "コンパイラ エラー C2635 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2635
dev_langs:
- C++
helpviewer_keywords:
- C2635
ms.assetid: 9deca2a8-2d61-42eb-9783-6578132ee3fb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 717e3979ac0f1309f24e6747946480b4e05ada42
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="compiler-error-c2635"></a>コンパイラ エラー C2635
変換できません、' identifier1 *'、' identifier2\*'; 仮想基底クラスからの変換は暗黙的に指定  
  
 変換からのキャストが必要です、`virtual`基底クラスを派生クラスでは許可されていません。  
  
 次の例では、C2635 が生成されます。  
  
```  
// C2635.cpp  
class B {};  
class D : virtual public B {};  
class E : public B {};  
  
int main() {  
   B b;  
   D d;  
   E e;  
  
   D * pD = &d;  
   E * pE = &e;  
   pD = (D*)&b;   // C2635  
   pE = (E*)&b;   // OK  
}  
```