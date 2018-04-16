---
title: "呼び出し元の呼び出し先保存済みレジスタ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 61e8d57c177ded8102f257cf84adedc0de0e312a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="callercallee-saved-registers"></a>呼び出し元または呼び出し先保存済みレジスタ
関数の呼び出しでは揮発性と見なされ、考慮すべき RAX、RCX、RDX、R8、R9、R10、R11 レジスタが破棄されます (しない限り、それ以外の場合の安全性の立証可能なプログラム全体の最適化などの分析で)。  
  
 レジスタ RBX、RBP、RDI、RSI、RSP、R12、R13、R14、および R15 不揮発性と見なされます保存する必要がありますや関数によって復元されるそれらを使用します。  
  
## <a name="see-also"></a>参照  
 [呼び出し規則](../build/calling-convention.md)