---
title: "コンパイラの警告 (レベル 1) C4167 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4167
dev_langs: C++
helpviewer_keywords: C4167
ms.assetid: 74a420bd-9371-4167-b1ee-74dd8680f97b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 68786d5d93d587af745a04d10f9daaf7b2fb734e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4167"></a>コンパイラの警告 (レベル 1) C4167
function : 組み込み関数としてのみ使用可能です  
  
 **#pragma function** が、組み込み形式で使用する必要がある関数に対して従来の呼び出しを使用するよう、コンパイラを強制しようとしています。 このプラグマは無視されます。  
  
 この警告を回避するには、 **#pragma function**を削除します。  
  
## <a name="example"></a>例  
  
```  
// C4167.cpp  
// compile with: /W1  
#include <malloc.h>  
#pragma function(_alloca )   // C4167: _alloca() is intrinsic only  
int main(){}  
```