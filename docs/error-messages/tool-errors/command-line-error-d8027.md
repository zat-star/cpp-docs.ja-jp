---
title: "コマンド ライン エラー D8027 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D8027
dev_langs: C++
helpviewer_keywords: D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8e52c3c3029a8828aef11637a21f862cbe33cf9f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="command-line-error-d8027"></a>コマンド ライン エラー D8027
'コンポーネント' を実行できません。  
  
 特定のコンパイラ コンポーネントまたはリンカー、コンパイラは実行できませんでした。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  メモリ不足のため、コンポーネントを読み込めません。 (Nmake の) に、コンパイラが呼び出される場合は、外部メイクファイルでコンパイラを実行します。  
  
2.  現在のオペレーティング システムでは、コンポーネントは実行できませんでした。 確認パス ポイント実行可能ファイルをオペレーティング システムに合った適切なします。  
  
3.  コンポーネントが破損しています。 セットアップ プログラムを使用して、パッケージ内のディスクからのコンポーネントを再コピーします。  
  
4.  オプションが正しく指定されていません。 例:  
  
    ```  
    cl /B1 file1.c  
    ```