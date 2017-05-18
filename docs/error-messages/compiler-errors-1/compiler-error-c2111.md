---
title: "コンパイラ エラー C2111 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2111
dev_langs:
- C++
helpviewer_keywords:
- C2111
ms.assetid: 38fd42ec-1480-4a44-aaca-ae4593ed5f50
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c13794a88bd7e78b0ba7b9616164ecf734f95c67
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2111"></a>コンパイラ エラー C2111
'+': ポインターに整数でない値を加えようとしました  
  
 プラス ( `+` ) 演算子を使用してポインターに整数でない値を追加しようとしました。  
  
 次の例では C2111 が生成されます。  
  
```  
// C2111.cpp  
int main() {  
   int *a = 0, *pa = 0, b = 0;  
   double d = 0.00;  
  
   a = pa + d;   // C2111  
   a = pa + b;   // OK  
}  
```
