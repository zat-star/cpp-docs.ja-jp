---
title: "コンパイラ エラー C2868 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2868
dev_langs: C++
helpviewer_keywords: C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7255aa3e73e23109535ae0e83d6e9bd907cdbcd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2868"></a>コンパイラ エラー C2868  
  
> '*識別子*': using 宣言の構文上の誤りです予期される修飾名。  
  
A[宣言を使用して](../../cpp/using-declaration.md)が必要です、*修飾名*、スコープ演算子 (`::`) 区切られた識別子名で終わる一連の名前空間、クラス、または列挙型名。 1 つのスコープ解決演算子は、グローバル名前空間から名前を導入するために可能性があります。  
  
## <a name="example"></a>例  
  
次の例では、C2868 を生成し、正しい使用法も示しています。  
  
```cpp  
// C2868.cpp  
class X {  
public:  
   int i;  
};  
  
class Y : X {  
public:  
   using X::i;   // OK  
};  
  
int main() {  
   using X;   // C2868  
}  
```