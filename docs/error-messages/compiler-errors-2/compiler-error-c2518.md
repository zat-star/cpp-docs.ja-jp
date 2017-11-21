---
title: "コンパイラ エラー C2518 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2518
dev_langs: C++
helpviewer_keywords: C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2a76c528def49b1235460fa4d6632efd196417d3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2518"></a>コンパイラ エラー C2518
キーワード 'keyword' の基底クラス リストに無効です無視されます。  
  
 キーワード`class`と`struct`が、基底クラス リストに表示されません。  
  
 次の例では、C2518 が生成されます。  
  
```  
// C2518.cpp  
// compile with: /c  
class B {};  
class C : public class B {};   // C2518  
class D: public B {};   // OK  
```