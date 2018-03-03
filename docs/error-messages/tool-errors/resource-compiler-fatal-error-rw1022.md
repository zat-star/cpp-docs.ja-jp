---
title: "リソース コンパイラの致命的なエラー RW1022 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RW1022
dev_langs:
- C++
helpviewer_keywords:
- RW1022
ms.assetid: 6747c8a9-9c9b-4422-b414-0645d22092d0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a78e54496b1b0db11d8b6d6f85b5142db0d4ad6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rw1022"></a>リソース コンパイラの致命的なエラー RW1022
**ファイルの書き込み I/O エラー**  
  
 リソース コンパイラは、ファイルに書き込めませんでした。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  ディスク領域が不足しています。 空き領域を作成する実行可能ファイルのサイズの少なくとも 2 倍に等しくなければなりません。  
  
2.  ボリュームが読み取り専用です。  
  
3.  正しくないセクターです。  
  
4.  共有違反です。