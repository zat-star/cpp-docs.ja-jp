---
title: "コンパイラ エラー C2062 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2062
dev_langs: C++
helpviewer_keywords: C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4a006bed55f16e6ed94c3b5ed9415320acb86fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2062"></a>コンパイラ エラー C2062
型 'type' の予期しません。  
  
 コンパイラでは、型名が想定されていませんでした。  
  
 次の例では、c2062 エラーが生成されます。  
  
```  
// C2062.cpp  
// compile with: /c  
struct A {  : int l; };   // C2062  
struct B { private: int l; };   // OK  
```  
  
 C2062 エラーも発生する可能性が方法、コンパイラによってコンス トラクターのパラメーター リストで定義されていない型の処理です。 コンパイラには、未定義の型 (スペルの正しくないですか?) が発生すると、コンス トラクターは、式を指定し、c2062 が前提とします。 解決するには、のみを使用するには、コンス トラクターのパラメーター リスト内の型を定義します。