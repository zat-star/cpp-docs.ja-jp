---
title: "コンパイラ エラー C2324 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2324
dev_langs: C++
helpviewer_keywords: C2324
ms.assetid: 215f0544-85b0-452d-825f-17a388b6a61c
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 10685a5e1692345b3ce4198dd2815763dd053ff9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2324"></a>コンパイラ エラー C2324
'identifier': 'name' の右側に予期しません。  
  
 正しくない識別子を使用して、デストラクターが呼び出されます。  
  
 次の例では、C2324 が生成されます。  
  
```  
// C2324.cpp  
class A {};  
typedef A* pA_t;  
int i;  
  
int main() {  
   pA_t * ppa = new pA_t;  
   ppa->~i;   // C2324  
   ppa->~pA_t();   // OK  
}  
```