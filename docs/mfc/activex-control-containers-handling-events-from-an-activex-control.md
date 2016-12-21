---
title: "ActiveX コントロール コンテナー : ActiveX コントロールで発生したイベントの処理 | Microsoft Docs"
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
  - "ActiveX コントロール コンテナー [C++], イベント シンク"
  - "ActiveX コントロール [C++], イベント"
  - "BEGIN_EVENTSINK_MAP マクロ"
  - "END_EVENTSINK_MAP マクロ, 使用"
  - "イベント ハンドラー [C++], ActiveX コントロール"
  - "イベント処理 [C++], ActiveX コントロール"
  - "イベント [C++], ActiveX コントロール"
  - "ON_EVENT マクロ"
ms.assetid: f9c106db-052f-4e32-82ad-750646aa760b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX コントロール コンテナー : ActiveX コントロールで発生したイベントの処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ActiveX コントロール コンテナーに ActiveX コントロールのイベント ハンドラーをインストールするには、プロパティ ウィンドウを使用する方法について説明します。  イベント ハンドラーが特定のイベント通知 \(コントロール\) から受け取り、応答で操作を実行するために使用されます。  この通知は「イベントの発生」と呼ばれます。  
  
> [!NOTE]
>  ここでは、プロシージャ コードで ActiveX コントロール コンテナー ダイアログ ベースのプロジェクトによって Container という名前の例として、Circ という名前の埋め込みコントロールを使用します。  
  
 プロパティ ウィンドウのイベント ボタンを使用して、ActiveX コントロール コンテナー アプリケーションで発生するイベント マップを作成できます。  「イベント シンク マップと呼ばれるこのマップに追加すると」、コントロール コンテナー クラスにイベント ハンドラーを Visual C\+\+ で作成および保持されます。  イベント マップ エントリに実装される各イベント ハンドラーは、コンテナーのイベント ハンドラーのメンバー関数に特定のイベントを割り当てます。  このイベント ハンドラー関数は、指定したイベントが ActiveX コントロール オブジェクトから発生したときに呼び出されます。  
  
 イベント シンク マップの詳細については、" MFC *リファレンス*"の [イベント シンク マップ](../mfc/reference/event-sink-maps.md) を参照します。  
  
##  <a name="_core_event_handler_modifications_to_the_project"></a> プロジェクトへのイベント ハンドラーの変更  
 イベント ハンドラーを追加するには、プロパティ ウィンドウを使用すると、イベント シンク マップはプロジェクトで宣言および定義されます。  次のステートメントはコントロール .cpp ファイルにイベント ハンドラーが追加されたときに追加されます。  このコードは、ダイアログ ボックス クラス \(この場合は `CContainerDlg`\) のイベント シンク マップを宣言します:  
  
 [!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/CPP/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]  
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/CPP/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]  
  
 イベントを追加するには、プロパティ ウィンドウを使用するとイベント マップ エントリ \(`ON_EVENT`\) は、コンテナーの実装 \(.cpp\) ファイルにイベント シンク マップとイベント ハンドラー関数に追加される追加されます。  
  
 次の例は、Circ のコントロールの **ClickIn** イベントの `OnClickInCircCtrl`と、呼び出されたイベント ハンドラーを宣言します:  
  
 [!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/CPP/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]  
  
 また、次のテンプレートは、イベント ハンドラーのメンバー関数の `CContainerDlg` クラス実装 \(.cpp\) ファイルに追加します:  
  
 [!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/CPP/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]  
  
 イベント シンク マクロの詳細については、" MFC *リファレンス*"の [イベント シンク マップ](../mfc/reference/event-sink-maps.md) を参照します。  
  
#### イベント ハンドラー関数を作成するには  
  
1.  クラス ビューから、ActiveX コントロールを含むダイアログ クラスを選択します。  この例では、`CContainerDlg`を使用します。  
  
2.  \[プロパティ\] ウィンドウの **\[イベント\]** をクリックします。  
  
3.  プロパティ ウィンドウで、埋め込まれたな ActiveX コントロールのコントロール ID を選択します。  この例では、`IDC_CIRCCTRL1`を使用します。  
  
     プロパティ ウィンドウが埋め込まれたな ActiveX コントロールによって発生するイベントの一覧が表示されます。  太字で示したメンバー関数が既に、割り当てられたハンドラー関数があります。  
  
4.  このダイアログ クラスに処理して作成するイベントを選択します。  この例では、**クリック**を選択します。  
  
5.  右側のドロップダウン リスト ボックスで、**\<Add\> ClickCircctrl1**を選択します。  
  
6.  `CContainerDlg`の実装 \(.cpp\) ファイルのイベント ハンドラー コードにジャンプするには、クラス ビューの new ハンドラー関数をダブルクリックします。  
  
## 参照  
 [ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)