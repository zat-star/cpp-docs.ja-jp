---
title: "コンパイラ エラー C2646 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2646
dev_langs: C++
helpviewer_keywords: C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0d9572f7d8e0b3eb01288d7dff414def8be2b203
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2646"></a>コンパイラ エラー C2646
グローバルまたは名前空間スコープの匿名構造体または匿名共用体は静的に宣言する必要があります  
  
 匿名構造体または匿名共用体にはグローバル スコープまたは名前空間のスコープがありますが、`static` 宣言されていません。  
  
 次の例では、C2646 を生成し、その修正方法を示しています。  
  
```  
// C2646.cpp  
// compile with: /c  
union { int i; };   // C2646 not static  
  
// OK  
static union { int j; };  
union U { int i; };  
```