---
title: "コンパイラの警告 (レベル 1) C4806 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4806
dev_langs: C++
helpviewer_keywords: C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1a9c9c48f01746aaf208db28ce84fe006e990aaf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4806"></a>コンパイラの警告 (レベル 1) C4806
'operation': 安全でない演算: 'type' 型から 'type' 型への上位変換を行うと与えられた定数に等しくなりません  
  
 このメッセージは、 `b == 3`に `b` 型がある `bool`などのコードに対して警告を行います。 上位変換の規則に従って、 `bool` が `int`に上位変換されます。 これは有効ですが、 **true**にすることはできません。 次の例では C4806 が生成されます。  
  
```  
// C4806.cpp  
// compile with: /W1  
int main()  
{  
   bool b = true;  
   // try..  
   // int b = true;  
  
   if (b == 3)   // C4806  
   {  
      b = false;  
   }  
}  
```