---
title: "コンパイラ エラー C2391 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2391
dev_langs: C++
helpviewer_keywords: C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 573cea44b0a39ff3cc0dff4469aa8c5f5a2459e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2391"></a>コンパイラ エラー C2391
'identifier': 'friend' を型定義中に使用することはできません  
  
 `friend`宣言には、完全なクラス宣言が含まれています。 A`friend`宣言を指定できますが、メンバー関数、または、詳細な型指定子を完全なクラス宣言ではありません。  
  
 次の例では C2326 が生成されます。  
  
```  
// C2391.cpp  
// compile with: /c  
class D {   
   void func( int );   
};  
  
class A {  
   friend class B { int i; };   // C2391  
  
   // OK  
   friend class C;  
   friend void D::func(int);  
};  
```