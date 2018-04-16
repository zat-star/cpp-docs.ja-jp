---
title: "コンパイラ エラー C2500 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a7be7320c21469536f6ddada99abd862812d882
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2500"></a>コンパイラ エラー C2500
'identifier1': 'identifier2' である直接基底クラス  
  
 クラスまたは構造体の基底クラスの一覧に 2 回以上表示されます。  
  
 直接の基本クラスは基底のリストに記載されています。 間接基本は、基底のリスト内のクラスのいずれかの基本クラスです。  
  
 クラスは、直接基底クラスとして複数回指定できません。 クラスは、間接基底クラスとして複数回使用できます。  
  
 次の例では、C2500 が生成されます。  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```