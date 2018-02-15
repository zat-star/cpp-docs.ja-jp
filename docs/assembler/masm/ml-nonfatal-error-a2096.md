---
title: "ML の致命的でないエラー A2096 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A2096
dev_langs:
- C++
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5c19796f10f40b8705aca024be3131de2da56501
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="ml-nonfatal-error-a2096"></a>ML の致命的でないエラー A2096
**セグメント、グループ、またはセグメント レジスタが必要です。**  
  
 セグメントまたはグループが必要でしたが、見つかりませんでした。  
  
 次のいずれかが発生しました。  
  
-   セグメントに指定した左オペランドに演算子がオーバーライド (**:**) セグメント レジスタ (CS、DS、SS、ES、FS、または GS)、グループ名、セグメント名、またはセグメント式ありませんでした。  
  
-   [想定](../../assembler/masm/assume.md)ディレクティブは、セグメント レジスタに有効なセグメントのアドレス、セグメント レジスタ、グループ、または特別なを指定しました**フラット**グループ。  
  
## <a name="see-also"></a>参照  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)