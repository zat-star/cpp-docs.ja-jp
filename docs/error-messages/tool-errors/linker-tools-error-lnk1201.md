---
title: "リンカ ツール エラー LNK1201 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1201
dev_langs: C++
helpviewer_keywords: LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 344f56eb3097bad447d9a0b12a0c5aac6f68b119
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1201"></a>リンカ ツール エラー LNK1201
プログラム データベース 'filename' への書き込みエラーディスク領域の不足、無効なパス、または十分な特権の確認します。  
  
 リンクは、出力ファイルのプログラム データベース (PDB) に書き込めませんでした。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  ファイルが壊れています。 PDB ファイルと再リンクを削除します。  
  
2.  ファイルの書き込みにディスク領域が十分ではありません。  
  
3.  ドライブは、ネットワークの問題の原因として考えられます。  
  
4.  デバッガーは、リンクしようとしているプログラム上でアクティブです。  
  
5.  ヒープ領域不足。  参照してください[C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)詳細についてはします。