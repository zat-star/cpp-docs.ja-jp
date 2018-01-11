---
title: "コンパイラ エラー C2998 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2998
dev_langs: C++
helpviewer_keywords: C2998
ms.assetid: 8193d491-b5d9-4477-acb1-cf166889c070
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04dbaa32e5fdde406bf5dc4a97febbc9a95d1c56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2998"></a>コンパイラ エラー C2998
'identifier': テンプレート定義ではありません  
  
 コンパイラはテンプレート定義で使用されている構文を処理できませんでした。  
  
 次の例では C2998 が生成されます。  
  
```  
// C2998.cpp  
// compile with: /c  
template <class T> int x = 1018; // C2998  
```