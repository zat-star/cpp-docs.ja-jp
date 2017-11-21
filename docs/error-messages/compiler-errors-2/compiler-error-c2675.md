---
title: "コンパイラ エラー C2675 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2675
dev_langs: C++
helpviewer_keywords: C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c9c5815e7c57eb2469599a26c2cbc5202018f27e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2675"></a>コンパイラ エラー C2675
単項 'operator': 'type' はいないこの演算子または定義を適切な型への変換を定義済の演算子に  
  
 C2675 は、単項演算子を使用する場合にも発生することができ、型が定義されていない演算子は、適切な型への変換を定義済の演算子にします。 この演算子を使うには、型を指定してこの演算子をオーバーロードするか、この演算子が定義された型への変換を定義する必要があります。  
  
## <a name="example"></a>例  
 次の例では、C2675 を生成します。  
  
```  
// C2675.cpp  
struct C {   
   C(){}  
} c;  
  
struct D {   
   D(){}  
   void operator-(){}  
} d;  
  
int main() {  
   -c;   // C2675  
   -d;   // OK  
}  
```