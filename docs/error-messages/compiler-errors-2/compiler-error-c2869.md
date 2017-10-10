---
title: "コンパイラ エラー C2869 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2869
dev_langs:
- C++
helpviewer_keywords:
- C2869
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ebdd6a371f20a03db3677f038155c40bfa2e75ab
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2869"></a>コンパイラ エラー C2869
'name': 名前空間として既に定義されています  
  
 名前空間として既に使用される名前を再利用することはできません。  
  
 次の例では、C2869 が生成されます。  
  
```  
// C2869.cpp  
// compile with: /c  
namespace A { int i; };  
  
class A {};   // C2869, A is already used  
```
