---
title: "コンパイラ エラー C2970 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2970
dev_langs: C++
helpviewer_keywords: C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e29ed219cf0e2faba8d1c12709432a9069c5aacf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2970"></a>コンパイラ エラー C2970
'class': テンプレート パラメーター 'param': 'arg': 非型引数として内部リンケージを持つオブジェクトを含む式を使用することはできません  
  
 テンプレート引数としては、名前または静的変数のアドレスを使うことはできません。 このテンプレート クラスでは、コンパイル時に評価される定数値が必要です。  
  
 次の例では、C2970 が生成されます。  
  
```  
// C2970.cpp  
// compile with: /c  
static int si;  
// could declare nonstatic to resolve all errors  
// int si;  
  
template <int i>   
class X {};  
  
template <int *pi>   
class Y {};  
  
X<si> anX;   // C2970 cannot use static variable in templates  
  
// this would also work  
const int i = 10;  
X<i> anX2;  
```