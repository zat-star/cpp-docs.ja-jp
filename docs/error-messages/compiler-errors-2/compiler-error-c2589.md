---
title: "コンパイラ エラー C2589 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2589
dev_langs: C++
helpviewer_keywords: C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5301caf0b52e61000a804e1d73b76343a8b7b2eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2589"></a>コンパイラ エラー C2589
'identifier': の右側に無効なトークン ':: '  
  
 クラス、構造体、または共用体の名前が、スコープ解決演算子 (ダブル コロンを含む) の左側に表示された場合、右側のトークンは、クラス、構造体、または共用体のメンバーにする必要があります。 それ以外の場合、任意のグローバル識別子は、右側に表示できます。  
  
 スコープ解決演算子をオーバー ロードできません。  
  
 次の例では、C2589 が生成されます。  
  
```  
// C2589.cpp  
void Test(){}  
class A {};  
void operator :: ();   // C2589  
  
int main() {  
   ::Test();  
}  
```