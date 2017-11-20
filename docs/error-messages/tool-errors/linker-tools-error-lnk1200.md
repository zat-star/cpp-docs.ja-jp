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
ms.openlocfilehash: 792c81e36b99bbac6c0417f0230bb1ea2bb1787c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1200"></a>リンカ ツール エラー LNK1200
プログラム データベース 'filename' を読み取り中にエラー  
  
 プログラム データベース (PDB) が読み取れませんでした。  
  
 このエラーは、ファイルの破損によって発生することができます。  
  
 場合`filename`PDB は、オブジェクト ファイルの場合、ファイルを使用してオブジェクトを再コンパイル[/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)です。  
  
 場合`filename`PDB と再リンクの削除、メイン出力ファイルの PDB は、インクリメンタル リンク中にこのエラーが発生しました。