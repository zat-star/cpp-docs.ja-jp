---
title: "コンパイラ エラー C2632 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2632
dev_langs:
- C++
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c1af198d4949da112792c2bbddfac68a80d0daf4
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

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
