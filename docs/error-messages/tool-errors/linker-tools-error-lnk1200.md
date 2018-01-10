---
title: "リンカ ツール エラー LNK1200 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1200
dev_langs: C++
helpviewer_keywords: LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 70bf262d4f99c807e3488c1f9b2ed9e73b1eb715
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1200"></a>リンカ ツール エラー LNK1200
プログラム データベース 'filename' を読み取り中にエラー  
  
 プログラム データベース (PDB) が読み取れませんでした。  
  
 このエラーは、ファイルの破損によって発生することができます。  
  
 場合`filename`PDB は、オブジェクト ファイルの場合、ファイルを使用してオブジェクトを再コンパイル[/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)です。  
  
 場合`filename`PDB と再リンクの削除、メイン出力ファイルの PDB は、インクリメンタル リンク中にこのエラーが発生しました。