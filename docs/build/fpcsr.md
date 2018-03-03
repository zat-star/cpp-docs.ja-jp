---
title: "FpCsr |Microsoft ドキュメント"
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
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15b7caebc99c4724c0e28b7812da8ef224184385
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fpcsr"></a>FpCsr
レジスタの状態も含まれますは x87 FPU 制御ワードです。 呼び出し規約では、このレジスタを不揮発性によって決まります。  
  
 X87 FPU 制御ワードのレジスタの開始時に、次の標準的な値に設定されているプログラムの実行。  
  
```  
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)  
FPCSR[7]: Reserved - 0  
FPCSR[8:9]: Precision Control - 10B (double precision)  
FPCSR[10:11]: Rounding  control - 0 (round to nearest)  
FPCSR[12]: Infinity control - 0 (not used)  
```  
  
 FPCSR 内のフィールドのいずれかを変更する呼び出し先が呼び出し元に返す前にそれらを復元する必要があります。 さらに、呼び出し元がこれらのフィールドのいずれかを変更する必要があります値に戻す、標準呼び出し先契約には、変更された値が必要ですがない限り、呼び出し先を呼び出す前にします。  
  
 これには、制御フラグの不揮発性に関する規則に 2 つの例外があります。  
  
1.  ここで指定された関数の文書化されている目的は、不揮発性 FpCsr を変更する関数にフラグを設定します。  
  
2.  おそらくである場合は、プログラムが動作/手段でこれらの規則に違反しない、たとえば、プログラム全体の分析によって、プログラムと同じ結果をこれらの規則に違反するを修正します。  
  
## <a name="see-also"></a>参照  
 [呼び出し規則](../build/calling-convention.md)