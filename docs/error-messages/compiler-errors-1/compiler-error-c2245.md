---
title: "コンパイラ エラー C2245 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2245
dev_langs: C++
helpviewer_keywords: C2245
ms.assetid: 08aaeadf-10ec-485a-b2a6-6e775289082b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aa96c1afce7d53fc8e4fe815349553ce02dfb87a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2245"></a>コンパイラ エラー C2245
friend と指定された存在しないメンバー関数 'function' (メンバー関数署名がオーバーロードと一致しません)  
  
 フレンドとして指定された関数がコンパイラによって検出されませんでした。  
  
 次の例では C2245 が生成されます。  
  
```  
// C2245.cpp  
// compile with: /c  
class B {  
   void f(int i);  
};  
  
class A {  
   int m_i;  
   friend void B::f(char);   // C2245  
   // try the following line instead  
   // friend void B::f(int);  
};  
  
void B::f(int i) {  
   A a;  
   a.m_i = 0;  
}  
```