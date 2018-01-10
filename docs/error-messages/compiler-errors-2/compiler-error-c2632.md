---
title: "コンパイラ エラー C2632 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2632
dev_langs: C++
helpviewer_keywords: C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 03a6d75ab9af6cd45ef982ff9d2e12640266c1b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2632"></a>コンパイラ エラー C2632
'type1' が 'type2' 続くことはできません。  
  
 このエラーは、次の 2 つの型指定子の間にコードがない場合に発生することができます。  
  
 次の例では、C2632 が生成されます。  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 このエラーは、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成できます。 `bool`適切な型ではようになりました。 以前のバージョンで`bool`が、typedef と同じ名前の識別子を作成できます。  
  
 次の例では、C2632 が生成されます。  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 このエラーを解決するには、コードは、Visual Studio .NET 2003 と Visual Studio .NET のバージョンの Visual C では無効にできるようにするには、識別子を変更します。