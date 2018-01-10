---
title: "コンパイラ エラー C2886 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2886
dev_langs: C++
helpviewer_keywords: C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 464b593c3639f66a6afc7a165a22b5d327c86671
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2886"></a>コンパイラ エラー C2886
':identifier': シンボルをメンバー using 宣言で使用することはできません  
  
 A`using`宣言で名前空間の名前などのシンボルを使用します。 A`using`宣言は基底クラスのメンバーを宣言する用です。  
  
 次の例では、C2886 が生成されます。  
  
```  
// C2886.cpp  
// compile with: /c  
namespace Z {  
    int i;  
}  
  
class B {  
protected:  
    int i;  
};  
  
class D : public B {  
    // Error: Z is a namespace  
    using Z::i;   // C2886  
  
    // OK: B is a base class  
    using B::i;  
};  
```