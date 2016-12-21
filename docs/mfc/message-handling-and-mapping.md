---
title: "メッセージの処理とマップ | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "メッセージ処理"
  - "メッセージ マップ"
  - "MFC, メッセージ"
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メッセージの処理とマップ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この記事のファミリがメッセージとコマンドを MFC フレームワークによって処理される方法と、をハンドラー関数に関連付ける方法について説明します。  
  
 Windows の通常のプログラムでは、Windows メッセージは、ウィンドウ プロシージャの大きな switch ステートメントで処理されます。  MFC ではなく、別のクラス メンバー関数に直接メッセージをマップするために [メッセージ マップ](../mfc/message-categories.md) を使用します。  メッセージ マップは仮想関数がこのように効率的であり、メッセージが文書化し、検索など、最も適切な C\+\+ のオブジェクト アプリケーションによって処理されるようにようにします。  メッセージの一つのメッセージや範囲をマップし、ID に指示または ID を制御できます。  
  
 **WM\_COMMAND** メッセージ—通常、メニュー、ツール バー ボタン、またはアクセラレータで生成された—、メッセージ マップ機構を使用します。  MFC は、プログラムのアプリケーション、フレーム ウィンドウ、ビュー、アクティブ ドキュメント間のコマンド メッセージの標準 [ルーティングする。](../mfc/command-routing.md) を定義します。  必要な場合は、このルーティングをオーバーライドできます。  
  
 メッセージ マップもユーザー インターフェイス オブジェクトを更新する方法 \(メニューとツール バー ボタンなど\) を指定し、それを現在のコンテキストに合うようにするか、無効にします。  
  
 Windows メッセージ、メッセージ キューに関する一般的な情報については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [メッセージとメッセージ キュー](http://msdn.microsoft.com/library/windows/desktop/ms632590) を参照してください。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)  
  
-   [フレームワークがメッセージ ハンドラーに問い合わせる場合](../mfc/how-the-framework-calls-a-handler.md)  
  
-   [フレームワークがメッセージ マップを検索します。](../mfc/how-the-framework-searches-message-maps.md)  
  
-   [メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)  
  
-   [関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)  
  
-   [ステータス バーのコマンドの情報を表示する方法](../Topic/How%20to:%20Display%20Command%20Information%20in%20the%20Status%20Bar.md)  
  
-   [ユーザーインターフェイス オブジェクトの動的更新](../mfc/how-to-update-user-interface-objects.md)  
  
-   [方法 : テンプレート クラスのメッセージ マップを作成する](../mfc/how-to-create-a-message-map-for-a-template-class.md)  
  
## 参照  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)