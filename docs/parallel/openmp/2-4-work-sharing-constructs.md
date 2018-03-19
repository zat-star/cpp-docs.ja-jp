---
title: "2.4 動作共有のコンストラクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 476e4e23b22527accaa095d80b827c95aed58c15
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="24-work-sharing-constructs"></a>2.4 動作共有のコンストラクト
Work-sharing コンス トラクターは、これを検出した、チームのメンバーのうち、関連するステートメントの実行を配布します。 動作共有ディレクティブでは、新しいスレッドが起動しないと、work-sharing コンス トラクターへのエントリに暗黙のバリアはありません。  
  
 動作共有のシーケンスの構築と**バリア**で発生するディレクティブは、チームの各スレッドで同じである必要があります。  
  
 OpenMP には、次の work-sharing コンス トラクターを定義し、これらは後に続くセクションで説明。  
  
-   **デ**ィレクティブ  
  
-   **セクションでは**ディレクティブ  
  
-   **1 つ**ディレクティブ