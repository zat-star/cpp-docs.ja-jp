---
title: "コンパイラ エラー C2694 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2694
dev_langs: C++
helpviewer_keywords: C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b81a6ee838a1d30928e8cebb8ef581c23644afcf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2694"></a>コンパイラ エラー C2694
'override': 基底クラスよりも制限の緩い例外の指定に仮想メンバー関数 'base' を持つ仮想関数をオーバーライドします。  
  
 仮想関数がオーバーライドされるが[/Za](../../build/reference/za-ze-disable-language-extensions.md)、制限の緩い関数をオーバーライドする必要がある[例外の指定](../../cpp/exception-specifications-throw-cpp.md)です。  
  
 次の例では、C2694 が生成されます。  
  
```  
// C2694.cpp  
// compile with: /Za /c  
class MyBase {  
public:  
   virtual void f(void) throw(int) {  
   }  
};  
  
class Derived : public MyBase {  
public:  
   void f(void) throw(...) {}   // C2694  
   void f2(void) throw(int) {}   // OK  
};  
```