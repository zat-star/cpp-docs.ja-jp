---
title: "コンパイラの警告 (レベル 4) C4211 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4211
dev_langs: C++
helpviewer_keywords: C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9e985dd1a2742fff675642b1dcd1bdddcd8d7379
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4211"></a>コンパイラの警告 (レベル 4) C4211
使用される標準の拡張機能: extern が static に再定義されています  
  
 既定 Microsoft 拡張機能 (/Ze)、再定義できます、`extern`識別子として**静的**です。  
  
## <a name="example"></a>例  
  
```  
// C4211.c  
// compile with: /W4  
extern int i;  
static int i;   // C4211  
  
int main()  
{  
}  
```  
  
 このような再定義は ANSI 互換では有効ではありません ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。  
  
## <a name="see-also"></a>関連項目  


