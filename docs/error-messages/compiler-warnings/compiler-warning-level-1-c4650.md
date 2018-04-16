---
title: "コンパイラの警告 (レベル 1) C4650 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4650
dev_langs:
- C++
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af10d05562c0c60c6a010e105441533362d058df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4650"></a>コンパイラの警告 (レベル 1) C4650
プリコンパイル済みヘッダー以外ではなく、デバッグ情報ヘッダーからのグローバル シンボルのみが使用できます。  
  
 プリコンパイル済みヘッダー ファイルは、Microsoft シンボリック デバッグ情報にコンパイルされませんでした。  
  
 リンクしているときに生成された実行可能ファイルまたはダイナミック リンク ライブラリ ファイルには、プリコンパイル済みヘッダーに含まれているローカル シンボルのデバッグ情報は含まれません。  
  
 この警告を回避でプリコンパイル済みヘッダー ファイルを再コンパイルを[/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)コマンド ライン オプションです。