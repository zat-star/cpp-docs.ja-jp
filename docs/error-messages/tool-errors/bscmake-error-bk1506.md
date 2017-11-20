---
title: "BSCMAKE エラー BK1506 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1506
dev_langs: C++
helpviewer_keywords: BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c792f28b29ca9abf8594fbe6e351c4782b149a61
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-error-bk1506"></a>BSCMAKE エラー BK1506
ファイル 'filename' を開くことができません [: 理由]  
  
 BSCMAKE では、ファイルを開くことができません。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  別のプロセスによってロックされているファイルです。 場合`reason`という**権限が拒否されました**、ファイル ブラウザーを使用することがあります。 [参照] ウィンドウを閉じて、ビルドを再試行してください。  
  
2.  ディスクがいっぱいです。  
  
3.  ハードウェア エラーです。  
  
4.  指定された出力ファイルは、同じ名前の既存のサブフォルダーがします。