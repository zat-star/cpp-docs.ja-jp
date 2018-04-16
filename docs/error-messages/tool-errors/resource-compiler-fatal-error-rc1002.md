---
title: "リソース コンパイラの致命的なエラー RC1002 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1002
dev_langs:
- C++
helpviewer_keywords:
- RC1002
ms.assetid: b43dfece-0dc3-4d0b-9d8f-509699b9ae80
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5343f0b6c1309dd4229ed6b34e282d6bc1f3f703
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1002"></a>リソース コンパイラの致命的なエラー RC1002
ヒープ スペースがありません。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  Windows のスワップ ファイルの領域を増やします。 詳細については、スワップ ファイルの容量を増やすと、Windows のヘルプ内の仮想メモリを参照してください。  
  
2.  小さなファイルに現在のファイルに分割し、個別にコンパイルします。  
  
3.  その他のプログラムまたはシステムで実行されているドライバーを削除します。