---
title: "メッセージ ハンドラー | Microsoft Docs"
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
  - "コマンド処理, メッセージ ハンドラー"
  - "ハンドラー"
  - "ハンドラー, コマンド"
  - "ハンドラー, メッセージ"
  - "メッセージ ハンドラー"
  - "メッセージ処理, メッセージ ハンドラー関数"
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メッセージ ハンドラー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC では、専用の *ハンドラー関数は*、それぞれ別のメッセージを処理します。  メッセージハンドラー関数は、クラスのメンバー関数です。  このドキュメントでは、用語 *メッセージ ハンドラー メンバー関数*、*メッセージ処理関数*は、*メッセージ ハンドラー*と *ハンドラーを* 同じように使用します。  一部のメッセージ ハンドラーも呼び出されます」。と「コマンド ハンドラー  
  
 メッセージ ハンドラーを記述することは、.NET Framework アプリケーションを作成する作業の大きな割合を使用します。  この記事のファミリにはメッセージ処理機能のしくみについて説明します。  
  
 ハンドラーは、内容がメッセージのしますか。  これは、メッセージに応答する内容に基づいて描画されます。  クラスのプロパティ ウィンドウを使用してハンドラーを作成し、ソース・コード エディターを使用してハンドラーのコードを入力します。  
  
 ハンドラーを記述するために Microsoft Visual C\+\+ と MFC のすべての機能を使用できます。  すべてのクラスの一覧については、" *MFC リファレンス"の*" [クラス ライブラリの概要](../mfc/class-library-overview.md) を参照してください。  
  
## 参照  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)