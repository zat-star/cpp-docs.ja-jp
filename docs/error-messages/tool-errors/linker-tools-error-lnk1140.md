---
title: "リンカ ツール エラー LNK1140 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1140
dev_langs: C++
helpviewer_keywords: LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a5a7bce157359d547f91ba2b560cf258e231b4a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1140"></a>リンカ ツール エラー LNK1140
プログラム データベース モジュールが多すぎます/PDB とのリンク: なし  
  
 プロジェクトには、4096 以上のモジュールが含まれています。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  使用して再リンク[/PDB: NONE](../../build/reference/pdb-use-program-database.md)です。  
  
2.  デバッグ情報なしには、一部のモジュールをコンパイルします。  
  
3.  モジュールの数を減らします。