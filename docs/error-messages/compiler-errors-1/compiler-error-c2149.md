---
title: "コンパイラ エラー C2149 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2149
dev_langs: C++
helpviewer_keywords: C2149
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3e181d4fc2d5ee10533d2a0e13142e827863d762
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2149"></a>コンパイラ エラー C2149
'identifier': 名前付きビットフィールドの幅が 0 です  
  
 名前を指定しない場合にのみ、ビット フィールドの幅を 0 にできます。  
  
 次の例では C2149 が生成されます。  
  
```  
// C2149.cpp  
// compile with: /c  
struct C {  
   int i : 0;   // C2149  
   int j : 2;   // OK  
};  
```