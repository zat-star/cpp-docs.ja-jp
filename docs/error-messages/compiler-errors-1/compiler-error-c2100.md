---
title: "コンパイラ エラー C2100 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2100
dev_langs: C++
helpviewer_keywords: C2100
ms.assetid: 9ed5ea11-9d55-4ddf-8b1a-162c74f3c390
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 799dba08ffb14126a26234b85c7ac4dd60b63633
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2100"></a>コンパイラ エラー C2100
無効な間接  
  
 間接演算子 ( `*` ) と一緒にの値に適用します。  
  
 次の例では、C2100 が生成されます。  
  
```  
// C2100.cpp  
int main() {  
   int r = 0, *s = 0;  
   s = &r;  
   *r = 200;   // C2100  
   *s = 200;   // OK  
}  
```