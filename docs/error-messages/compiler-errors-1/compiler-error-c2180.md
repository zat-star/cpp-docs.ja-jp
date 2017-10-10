---
title: "コンパイラ エラー C2180 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2180
dev_langs:
- C++
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 181309cca171c872a7c3767729a755d6e73bd288
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2180"></a>コンパイラ エラー C2180
制御式には、型 'type' が指定されています。  
  
 `if`、`while`、`for`、`do` のいずれかのステートメントの制御式は、`void` にキャストした式です。 この問題を解決するには、制御式を、`bool` を生成する制御式または `bool` に変換できる型に変更します。  
  
 次の例では C2180 が生成されます。  
  
```  
// C2180.c  
  
int main() {  
   while ((void)1)   // C2180  
      return 1;  
   while (1)         // OK  
      return 0;  
}  
```
