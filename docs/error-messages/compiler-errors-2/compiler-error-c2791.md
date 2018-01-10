---
title: "コンパイラ エラー C2791 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2791
dev_langs: C++
helpviewer_keywords: C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12f3377ae2c8b1de572c9a498a99fae3236274c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2791"></a>コンパイラ エラー C2791
'super' の不正な使用: 'class' には、基本クラスはありません。  
  
 キーワード[super](../../cpp/super.md)を任意の基本クラスを持たないクラスのメンバー関数のコンテキスト内で使用されました。  
  
 次の例では、C2791 が生成されます。  
  
```  
// C2791.cpp  
struct D {  
   void mf() {  
      __super::mf();   // C2791  
   }  
};  
```