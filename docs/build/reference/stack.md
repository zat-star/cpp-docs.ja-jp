---
title: "-スタック |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /stack
dev_langs:
- C++
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 21438bf8f214c10525aa7e9a5829f835b8a33f2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="stack"></a>/STACK
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションは、スタックのサイズをバイト単位で設定され、10 進数または C 言語表記で引数を使用します。 /STACK オプションは、実行可能ファイルのみに適用されます。  
  
 *予約*引数は、仮想メモリのスタック割り当ての合計を指定します。 指定した値を最も近い 4 バイトに切り上げられます。  
  
 省略可能な`commit`引数は、オペレーティング システムによって解釈される可能性があります。 Windows NT、Windows 95 および Windows 98 で`commit`に一度に割り当てる物理メモリの量を指定します。 仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。 高い`commit`値は、アプリケーションがより多くのスタック領域を必要がありますが、メモリ量と起動時間が増加時間を節約します。  
  
## <a name="see-also"></a>参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)