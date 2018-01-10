---
title: "コンパイラ エラー C3072 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3072
dev_langs: C++
helpviewer_keywords: C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ece5f46afb5b9ef985385dd77c8ea7aa9f82c94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3072"></a>コンパイラ エラー C3072
演算子 'operator' は ref クラスのインスタンスに適用することはできません。  
  
 単項を使用して '`operator` ' ref クラスのインスタンスをハンドル型に変換する演算子  
  
 CLR 型には、CLR 演算子、いないネイティブ (標準) 演算子が必要です。  詳細については、次を参照してください。[参照演算子の追跡](../../windows/tracking-reference-operator-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3072 を生成します。  
  
```  
// C3072.cpp  
// compile with: /clr  
ref class R {};  
  
int main() {  
   R r1;  
   R^ r2 = &r1;   // C3072  
   R^ r3 = %r1;   // OK  
}  
```