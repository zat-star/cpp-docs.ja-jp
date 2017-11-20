---
title: "コンパイラの警告 (レベル 1) C4230 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4230
dev_langs: C++
helpviewer_keywords: C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0197e214a697be5a8e1ecd35eadeceb494669aff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4230"></a>コンパイラの警告 (レベル 1) C4230
旧形式の使用: 修飾子/限定名が混在してです。修飾子は無視されます。  
  
 などの Microsoft 修飾子の前に修飾子を使用して`__cdecl`旧式の手段です。  
  
## <a name="example"></a>例  
  
```  
// C4230.cpp  
// compile with: /W1 /LD  
int __cdecl const function1();   // C4230 const ignored  
```