---
title: "リソース コンパイラの致命的なエラー RC1120 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1120
dev_langs:
- C++
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28a35cc2f932cdf655324d05c10bdb875aa895a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1120"></a>リソース コンパイラの致命的なエラー RC1120
、メモリ不足に必要なバイト数です。  
  
 リソース コンパイラは、ヒープに格納されたアイテムの記憶領域不足になりました。 通常これは、多数のシンボルを作成した結果です。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  Windows のスワップ ファイルの領域を増やします。 詳細については、スワップ ファイルの容量を増やすと、Windows のヘルプ内の仮想メモリを参照してください。  
  
2.  不要インクルード ファイル、特に、不必要な`#define`s と関数のプロトタイプ。  
  
3.  2 つ以上のファイルに現在のファイルに分割し、個別にコンパイルします。  
  
4.  その他のプログラムまたは大量のメモリを消費している可能性がある、システムで実行されているドライバーを削除します。