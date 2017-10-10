---
title: "コンパイラ エラー C2971 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2971
dev_langs:
- C++
helpviewer_keywords:
- C2971
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 81194765278adc82d57a7a95cc8528f1fd6e1ef3
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2971"></a>コンパイラ エラー C2971
'class': テンプレート パラメーター 'param': 'arg': 非型引数としてローカル変数を使用することはできません  
  
 テンプレート引数としては、名前またはローカル変数のアドレスを使うことはできません。  
  
 次の例では、C2971 が生成されます。  
  
```  
// C2971.cpp  
template <int *pi>   
class Y {};  
  
int global_var = 0;  
  
int main() {  
   int local_var = 0;  
   Y<&local_var> aY;   // C2971  
   // try the following line instead  
   // Y<&global_var> aY;  
}  
```
