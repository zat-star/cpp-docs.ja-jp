---
title: ML の致命的でないエラー A2085 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- A2085
dev_langs:
- C++
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29d0d58e5cd65c16c848b3cc05e10b9f57488639
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="ml-nonfatal-error-a2085"></a>ML の致命的でないエラー A2085
**命令またはレジスタが CPU の現在のモードでは許可されません。**  
  
 命令、レジスタ、または現在のプロセッサ モードの無効なキーワードを使用しようとしました。  
  
 たとえば、32 ビット レジスタが必要な[.386](../../assembler/masm/dot-386.md)またはそれ以降。 CR0 特権モードが必要などの制御レジスタ[.386P](../../assembler/masm/dot-386p.md)またはそれ以降。 このエラーが生成されます、 **NEAR32**、 **FAR32**、および**フラット**を必要とするキーワードです**。386**またはそれ以降。  
  
## <a name="see-also"></a>参照  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)