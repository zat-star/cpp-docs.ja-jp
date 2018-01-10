---
title: "コンパイラ エラー C3252 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3252
dev_langs: C++
helpviewer_keywords: C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dcecc8b45b6cc9d5fe511f36894f77dacd568434
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3252"></a>コンパイラ エラー C3252
'method': マネージ型または WinRT 型で、仮想メソッドのアクセシビリティを制限することはできません。  
  
 基底クラスの仮想メソッドまたはインターフェイスのいずれかのメソッドを実装するクラスは、そのメソッドのアクセスを制限することはできません。  
  
 インターフェイスのすべてのメソッドはパブリックです。  
  
 次の例では、C3252 を生成し、その修正方法を示しています。  
  
```  
// C3252.cpp  
// compile with: /clr /c  
ref class A {  
public:  
   virtual void f1() {}  
};  
  
ref class B : public A {  
// To fix, uncomment the following line:   
// public:      
   virtual void f1() override sealed {}   // C3252, make this method public  
};  
```