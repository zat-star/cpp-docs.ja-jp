---
title: "コンパイラ エラー C3207 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3207
dev_langs:
- C++
helpviewer_keywords:
- C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04aecf7f37d7e631a9dc07c7f029257c274f6538
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3207"></a>コンパイラ エラー C3207
'function': 'arg' の無効なテンプレート引数です。クラス テンプレートが必要です  
  
 テンプレート関数は、テンプレート template 引数を取るものと定義されています。 しかし、テンプレート型引数が渡されました。  
  
 次の例では C3207 が生成されます。  
  
```  
// C3207.cpp  
template <template <class T> class TT>  
void f(){}  
  
template <class T>  
struct S  
{  
};  
  
void f1()  
{  
   f<S<int> >();   // C3207  
   // try the following line instead  
   // f<S>();  
}  
```