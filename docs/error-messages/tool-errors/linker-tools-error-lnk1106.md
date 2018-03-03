---
title: "リンカ ツール エラー LNK1106 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1106
dev_langs:
- C++
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 793d788462a3a449c654c30ec874399a3bb85728
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1106"></a>リンカ ツール エラー LNK1106
無効なファイルまたはディスクがいっぱいです: の場所にシークできません。  
  
 ツールの読み取りまたは書き込みでしたいない`location`メモリ マップト ファイルにします。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  ディスクがいっぱいです。  
  
     領域を解放し、リンクを再度クリックします。  
  
2.  ネットワーク経由でリンクしようとしています。  
  
     いくつかのネットワークは、リンカーによって使用されるメモリ マップト ファイルを完全にはサポートしていません。 ローカル ディスクにリンクしてください。  
  
3.  ディスク上の不良ブロックです。  
  
     ディスクのハードウェアとオペレーティング システムでは、このようなエラーが検出が必要、ディスク チェック プログラムを実行することがあります。  
  
4.  ヒープ領域不足。  
  
     参照してください[C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)詳細についてはします。