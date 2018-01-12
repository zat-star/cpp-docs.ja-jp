---
title: "コンパイラ エラー C2251 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2251
dev_langs: C++
helpviewer_keywords: C2251
ms.assetid: fefe050c-f8d3-4316-b237-8007dbcdd3bf
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 88630a44f0038449499c2abe5c7c725599c96226
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2251"></a>コンパイラ エラー C2251
名前空間 'namespace' にはメンバー 'member' がありません。'member' は正しいですか。  
  
 コンパイラは、指定された名前空間で識別子を見つけられませんでした。  
  
 次の例では C2251 が生成されます。  
  
```  
// C2251.cpp  
// compile with: /c  
namespace A {  
   namespace B {  
      void f1();  
   }  
  
   using namespace B;  
}  
  
void A::f1() {}   // C2251  
void A::B::f1() {}   // OK  
```