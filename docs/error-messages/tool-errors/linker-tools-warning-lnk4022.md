---
title: "リンカー ツールの警告 LNK4022 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4022
dev_langs:
- C++
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e35974a72de349f94f2189f676b6dc955c48fab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4022"></a>リンカー ツールの警告 LNK4022
シンボル 'symbol' の一意の一致を見つけることができません。  
  
 リンクまたは LIB が複数検出に指定された装飾されていないシンボルの一致して、に関して、あいまいさが解決できませんでした。 出力ファイル (.exe、.dll、.exp、または .lib) は生成されません。 この警告の 1 つの警告が続く[LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md)ごとのシンボルを複製し、致命的なエラーが最後に[LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md)です。  
  
 この警告を回避するのには、修飾された形式で、シンボルを指定します。 実行[DUMPBIN](../../build/reference/dumpbin-options.md)装飾名のオブジェクトを参照してください。