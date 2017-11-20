---
title: "コンパイラ エラー C2679 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2679
dev_langs: C++
helpviewer_keywords: C2679
ms.assetid: 1a5f9d00-9190-4aa6-bc72-949f68ec136f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7b2eb3e0e55442ad4525dea266d4f1ebc4f87039
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2679"></a>コンパイラ エラー C2679
binary 'operator': 'type' 型の右側のオペランドを扱う演算子が見つかりません (または許容可能な変換はありません)  
  
 この演算子を使うには、型を指定してこの演算子をオーバーロードするか、この演算子が定義された型への変換を定義する必要があります。  
  
 次の例では、C2679 が生成されます。  
  
```  
// C2679.cpp  
class C {  
public:  
   C();   // no constructor with an int argument  
} c;  
  
class D {  
public:  
   D(int) {}  
   D(){}  
} d;  
  
int main() {  
   c = 10;   // C2679  
   d = 10;   // OK  
}  
```