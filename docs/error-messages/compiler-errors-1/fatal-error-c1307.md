---
title: "致命的なエラー C1307 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1307"
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1307
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロファイル データが集められてからプログラムが編集されました。  
  
 [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) を使用しているときに、\/LTCG:PGINSTRUMENT の後で再コンパイルされた入力モジュールをリンカーが検出しました。このモジュールは既存のプロファイル データとは既に無関係になったポイントに変更されています。  たとえば、再コンパイルされたモジュール内で呼び出し先が変更されると、C1307 が生成されます。  
  
 このエラーを解決するには、\/LTCG:PGINSTRUMENT を実行し、すべてのテスト実行をやり直してから、\/LTCG:PGOPTIMIZE を実行します。  \/LTCG:PGINSTRUMENT を実行できない場合にすべてのテスト実行をやり直すには、\/LTCG:PGOPTIMIZE ではなく \/LTCG:PGUPDATE を使用して最適化されたイメージを作成します。