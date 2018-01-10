---
title: "コンパイラ エラー C2801 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2801
dev_langs: C++
helpviewer_keywords: C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bbdbfdc1b7bb9445b1a709afb42944eea0d7f241
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2801"></a>コンパイラ エラー C2801
'operator 演算子' は非静的メンバーである必要があります。  
  
 非静的メンバーとしてのみ、次の演算子はオーバー ロードできます。  
  
-   割り当て`=`  
  
-   クラス メンバーへのアクセス`->`  
  
-   添字演算子`[]`  
  
-   関数呼び出し`()`  
  
 C2801 エラーの原因が考えられます。  
  
-   オーバー ロードされた演算子は、クラス、構造体、または共用体のメンバーではありません。  
  
-   オーバー ロードされた演算子が宣言されて`static`です。  
  
-   次の例では、C2801 が生成されます。  
  
```  
// C2801.cpp  
// compile with: /c  
operator[]();   // C2801 not a member  
class A {  
   static operator->();   // C2801 static  
   operator()();   // OK  
};  
```