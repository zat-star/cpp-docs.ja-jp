---
title: "リッチ エディット コントロールでのワード区切り | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "区切り文字 (CRichEditCtrl のワードの)"
  - "CRichEditCtrl クラス, ワード区切り"
  - "リッチ エディット コントロール, ワード区切り"
  - "単語の分割"
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リッチ エディット コントロールでのワード区切り
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リッチ エディット コントロール \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) は中断手順」という単語と関数呼び出しの間の中断を見つけ、改行のどこにあるかを確認します。  コントロールはワードラップ操作と CTRL\+LEFT と→キーの組み合わせを処理するときに実行するときに、この情報を使用します。  アプリケーションはリッチ エディット コントロールに既定の単語中断プロシージャを置き換え、Word 中断情報を取得し、必要な行で指定された文字があるかを判断するためにメッセージを送信できます。  
  
## 参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)