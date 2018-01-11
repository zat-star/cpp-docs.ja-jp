---
title: "コンパイラ エラー C2803 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2803
dev_langs: C++
helpviewer_keywords: C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2472c0e1182ad11f5ea95e3411649e6214b110ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2803"></a>コンパイラ エラー C2803
'operator 演算子' がクラス型の仮パラメーターを 1 つ以上あります。  
  
 オーバー ロードされた演算子には、クラス型のパラメーターが不足しています。  
  
 参照 (参照が、ポインターを使用していない) またはによって書き込むことができる値には、少なくとも 1 つのパラメーターを渡す必要がある"、< b"(の type クラス A と b)。  
  
 両方のパラメーターがポインターの場合はポインター アドレスの純粋な比較では、ユーザー定義の変換を使用しません。  
  
 次の例では、C2803 が生成されます。  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```