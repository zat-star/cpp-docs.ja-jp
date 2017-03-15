---
title: "ATL メッセージ ハンドラーの追加 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, メッセージ ハンドラー"
  - "ATL, ウィンドウ"
  - "メッセージ ハンドラー [C++]"
  - "メッセージ処理 [C++], ATL メッセージ ハンドラー"
  - "ウィンドウ [C++], ATL"
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL メッセージ ハンドラーの追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コントロールにメッセージ ハンドラー \(Windows メッセージを処理するメンバー関数\) を追加するには、まずクラス ビューでコントロールを選択します。  次 **\*\*\* プロパティ \*\*\*** のウィンドウを開き、**\[メッセージ\]** のアイコンを選択し、必要なメッセージのオブジェクトのボックスのドロップダウン コントロールをクリックします。  これは、コントロールの .cpp ファイルのスケルトン ハンドラーのヘッダー ファイルと実装のメッセージ ハンドラーの宣言を追加します。  また、メッセージ マップを追加し、ハンドラーのエントリが追加されます。  
  
 ATL メッセージ ハンドラーを追加すると、MFC クラスにメッセージ ハンドラーを追加することに似ています。  詳細については、[MFC のメッセージ ハンドラーを追加できます。](../mfc/reference/adding-an-mfc-message-handler.md) を参照してください。  
  
 次の条件は、ATL メッセージ ハンドラーを追加することだけです:  
  
-   メッセージ ハンドラーは、MFC と同じ名前付け規則に従います。  
  
-   新しいメッセージ マップのエントリはメイン メッセージ マップに追加されます。  ウィザードは代替メッセージ マップとチェーンを認識しません。  
  
## 参照  
 [ウィンドウの実装](../atl/implementing-a-window.md)