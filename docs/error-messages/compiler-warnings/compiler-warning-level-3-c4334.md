---
title: "コンパイラの警告 (レベル 3) C4334 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4334
dev_langs:
- C++
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7218caa399aec0bd1b9755fb6d0942991732121e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4334"></a>コンパイラの警告 (レベル 3) C4334
'operator': 64 ビットに 32 ビット シフトの結果が暗黙的に変換 (されました 64 ビット シフト目的としていますか?)  
  
 32 ビット シフトの結果は、64 ビットおよび 64 ビット シフトされたものである、コンパイラを疑いますに暗黙的に変換されました。  この警告を解決するには、64 ビット シフトを使用するか 64 ビットをシフトの結果を明示的にキャストします。  
  
## <a name="example"></a>例  
 次の例では、C4334 を生成します。  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```