---
title: "コンパイラの警告 (レベル 1) C4612 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 922da98a54a572462d2b247f6211a39bcaed9ec6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4612"></a>コンパイラの警告 (レベル 1) C4612
インクルード ファイル名にエラーがあります  
  
 この警告は、ファイル名が正しくないか、不足している場合に、 **#pragma include_alias** で発生します。  
  
 引数、 **#pragma include_alias**ステートメントから引用符を使用できます (**"***filename***"**) または山かっこ形式 (**\<**  *filename***>**)、両方とも同じ形式を使用する必要がありますが、します。  
  
## <a name="example"></a>例  
  
```  
// C4612.cpp  
// compile with: /W1 /LD  
#pragma include_alias("StandardIO", <stdio.h>) // C4612  
```