---
title: "コンパイラ エラー C2462 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2462
dev_langs:
- C++
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af4b7e303a67ed1eae3d217964818d1b4cd05b96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2462"></a>コンパイラ エラー C2462
'identifier': ' new' 演算子で型を定義することはできません  
  
 オペランド フィールドの種類を定義することはできません、`new`演算子。 別のステートメントで、種類の定義を配置します。  
  
 次の例では、C2462 が生成されます。  
  
```  
// C2462.cpp  
int main() {  
   new struct S { int i; };   // C2462  
}  
```