---
title: "ML の致命的でないエラー A2096 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2096
dev_langs: C++
helpviewer_keywords: A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d4466d87e33068b10b3f620bfbe764e4aec76c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2096"></a>ML の致命的でないエラー A2096
**セグメント、グループ、またはセグメント レジスタが必要です。**  
  
 セグメントまたはグループが必要でしたが、見つかりませんでした。  
  
 次のいずれかが発生しました。  
  
-   セグメントに指定した左オペランドに演算子がオーバーライド (**:**) セグメント レジスタ (CS、DS、SS、ES、FS、または GS)、グループ名、セグメント名、またはセグメント式ありませんでした。  
  
-   [想定](../../assembler/masm/assume.md)ディレクティブは、セグメント レジスタに有効なセグメントのアドレス、セグメント レジスタ、グループ、または特別なを指定しました**フラット**グループ。  
  
## <a name="see-also"></a>参照  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)