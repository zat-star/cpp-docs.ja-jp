---
title: "リンカ ツール エラー LNK1277 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1277"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1277"
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# リンカ ツール エラー LNK1277
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オブジェクトの記録が pgd \('filename'\) に見つかりません。  
  
 [\/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md) を使用したときに、.lib、def、または .obj の各入力ファイルのいずれかのパスが、\/LTCG:PGINSTRUMENT の実行中にそのファイルが検出されたパスと異なっていました。  これは、\/LTCG:PGINSTRUMENT の後で LIB 環境変数に変更が行われたことを示す場合があります。  入力ファイルへの完全パスは .pgd ファイルに格納されます。  
  
 \/LTCG:PGOPTIMIZE では、入力が \/LTCG:PGINSTRUMENT フェーズと同じであることが必要です。  
  
 この警告を解決するには、以下のいずれかの操作を実行します。  
  
-   \/LTCG:PGINSTRUMENT を実行し、すべてのテスト実行をやり直してから、\/LTCG:PGOPTIMIZE を実行します。  
  
-   LIB 環境変数を \/LTCG:PGINSTRUMENT を実行したときの設定に変更します。  
  
 \/LTCG:PGUPDATE を使用して LNK1277 を回避することはお勧めできません。