---
title: "ML の致命的なエラー A1011 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A1011
dev_langs:
- C++
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3a614bc56c76b220eeeb73ce2cc7e90a9ca9b8e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="ml-fatal-error-a1011"></a>ML の致命的なエラー A1011
**ディレクティブは、コントロール ブロックである必要があります。**  
  
 アセンブラーがいずれかのない、必要な高度なディレクティブが見つかりました。 次のディレクティブのいずれかが検出されました。  
  
-   [.ELSE](../../assembler/masm/dot-else.md)せず[です。もし](../../assembler/masm/dot-if.md)  
  
-   [.ENDIF](../../assembler/masm/dot-endif.md)せず[です。もし](../../assembler/masm/dot-if.md)  
  
-   [.ENDW](../../assembler/masm/dot-endw.md)せず[です。WHILE](../../assembler/masm/dot-while.md)  
  
-   [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md) without [.REPEAT](../../assembler/masm/dot-repeat.md)  
  
-   [.続行](../../assembler/masm/dot-continue.md)せず[です。中に](../../assembler/masm/dot-while.md)または[です。繰り返し](../../assembler/masm/dot-repeat.md)  
  
-   [.中断](../../assembler/masm/dot-break.md)せず[です。中に](../../assembler/masm/dot-while.md)または[です。繰り返し](../../assembler/masm/dot-repeat.md)  
  
-   [.ELSE](../../assembler/masm/dot-else.md)以下 `.ELSE`  
  
## <a name="see-also"></a>参照  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)