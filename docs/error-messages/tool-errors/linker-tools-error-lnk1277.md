---
title: "リンカ ツール エラー LNK1277 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1277
dev_langs: C++
helpviewer_keywords: LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3606207afc197dc26ac0540d476b74f52c0dc0a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1277"></a>リンカ ツール エラー LNK1277
オブジェクトのレコードが pgd (ファイル名) に見つかりませんでした。  
  
 使用する場合[/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md)、入力 .lib、def、または .obj ファイルの 1 つのパスが/LTCG:PGINSTRUMENT 中に検出されたパスと異なっています。 これは、/LTCG:PGINSTRUMENT 後に、LIB 環境変数での変更説明可能性があります。 入力ファイルへの完全パスは、.pgd ファイルに格納されます。  
  
 /LTCG:PGOPTIMIZE では、入力、/LTCG:PGINSTRUMENT フェーズに同一であることが必要です。  
  
 この警告を解決するには、次のいずれかの操作を行います。  
  
-   /LTCG:PGINSTRUMENT を実行し、すべてのテストの実行を再実行/LTCG:PGOPTIMIZE を実行します。  
  
-   /LTCG:PGINSTRUMENT を実行したときに、LIB 環境変数を変更します。  
  
 回避する LNK1277/LTCG:PGUPDATE を使用して、これは推奨されません。