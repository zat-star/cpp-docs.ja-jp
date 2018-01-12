---
title: "コンパイラ エラー C2600 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2600
dev_langs: C++
helpviewer_keywords: C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 407598a68df37aa130ce26e4f02e98de975ab527
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2600"></a>コンパイラ エラー C2600
'関数' : コンパイラで生成された特殊メンバー関数を定義できません (クラスで最初に宣言されなければなりません)  
  
 コンス トラクターやデストラクターなどのメンバー関数は、クラスに対して定義する前に、そのクラスで宣言する必要があります。 クラスで宣言されていない場合は、既定のコンス トラクターとデストラクター (特殊なメンバー関数と呼ばれます) をコンパイラで生成できます。 ただし、クラスに一致する宣言がない状態で、これらの関数のいずれかを定義すると、コンパイラによって競合が検出されます。  
  
 このエラーを修正するには、クラス宣言で、クラス宣言の外側で定義した各メンバー関数を宣言します。  
  
 次の例では警告 C2600 が生成されます。  
  
```  
// C2600.cpp  
// compile with: /c  
class C {};  
C::~C() {}   // C2600  
  
class D {  
   D::~D();  
};  
  
D::~D() {}  
```