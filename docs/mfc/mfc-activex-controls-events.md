---
title: "MFC ActiveX コントロール : イベント | Microsoft Docs"
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
  - "COleControl クラス, 処理 (イベントを)"
  - "コンテナー イベント"
  - "カスタム イベント, 追加 (ActiveX コントロールに)"
  - "イベント [C++], ActiveX コントロール"
  - "イベント [C++], マップ"
  - "マップ, イベント"
  - "MFC ActiveX コントロール, イベント"
  - "通知 [C++], 通知 (コンテナーにイベントを)"
  - "OLE イベント"
  - "ストック イベント"
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC ActiveX コントロール : イベント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロールは何かがコントロールになったコンテナーに通知するためにイベントを使用します。  イベントの一般的な例は、メニュー コントロール、キーボードを使用して入力されたデータをコントロールの状態の変更を示します。  これらのアクションが発生したときに、コントロールがコンテナーに通知するためにイベントを発生させます。  
  
 イベントは、メッセージと呼ばれます。  
  
 MFC には、2 種類のイベントをサポートする: ストック イベントとカスタム。  ストック イベントは [COleControl](../mfc/reference/colecontrol-class.md) ハンドルを自動的にラベル付けするイベントです。  ストック イベントの完全な一覧については、[MFC ActiveX コントロール: ストック イベントの追加](../Topic/MFC%20ActiveX%20Controls:%20Adding%20Stock%20Events%20to%20an%20ActiveX%20Control.md)記事を参照してください。  カスタム イベントは、コントロールに固有のアクションが発生したときにコントロールのコンテナーを通知する機能が用意されています。  たとえば、特定のコントロールまたはウィンドウ メッセージの受信側の内部状態の変更点です。  
  
 イベントを適切に実行するコントロールには、コントロール クラスを呼び出す必要のあるメンバー関数に関連するイベントが発生したときにコントロールの各イベントをマップする必要があります。  簡単にコントロールのイベントにアクセスし、処理するイベントと、Visual Studio に関するこの割り当て機能 \(イベント マップと呼ぶ\) 集中化する情報。  このイベント マップはヘッダーにある次のマクロで宣言されます。H\) コントロール クラス宣言のファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#2](../mfc/codesnippet/CPP/mfc-activex-controls-events_1.h)]  
  
 イベント マップを宣言した後、コントロールの実装 \(.cpp\) ファイルで定義する必要があります。  次のコードは、イベント マップを定義し、特定のイベントを発生させるようにコントロールがします:  
  
 [!code-cpp[NVC_MFC_AxUI#3](../mfc/codesnippet/CPP/mfc-activex-controls-events_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#4](../mfc/codesnippet/CPP/mfc-activex-controls-events_3.cpp)]  
  
 プロジェクトを作成したときに、MFC ActiveX コントロール ウィザードを使用すると、自動的に次の行を追加します。  MFC ActiveX コントロール ウィザードを使用して、次の行を手動で追加する必要があります。  
  
 クラス ビューを使用すると、定義したカスタム イベントまたは `COleControl` クラスでサポートされるストック イベントを追加できます。  新しいイベントでは、クラス ビューでは、コントロールのイベント マップとコントロールの .IDL ファイルに自動的に適切なエントリを追加します。  
  
 2 種類のそのほかのトピックはイベントを解説します:  
  
-   [MFC ActiveX コントロール: ストック イベントの追加](../Topic/MFC%20ActiveX%20Controls:%20Adding%20Stock%20Events%20to%20an%20ActiveX%20Control.md)  
  
-   [MFC ActiveX コントロール: カスタム イベントの追加](../Topic/MFC%20ActiveX%20Controls:%20Adding%20Custom%20Events.md)  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール : メソッド](../mfc/mfc-activex-controls-methods.md)   
 [COleControl クラス](../mfc/reference/colecontrol-class.md)