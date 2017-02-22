---
title: "MFC ActiveX コントロール : Windows コントロールのサブクラス化 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "precreatewindow"
  - "IsSubclassed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoSuperclassPaint メソッド"
  - "IsSubclassed メソッド"
  - "MFC ActiveX コントロール, 作成"
  - "MFC ActiveX コントロール, サブクラス コントロール"
  - "OnDraw メソッド, MFC ActiveX コントロール"
  - "PreCreateWindow メソッド, オーバーライド"
  - "リフレクション メッセージ, ActiveX コントロールで"
  - "サブクラス化"
  - "サブクラス化 (ウィンドウ コントロールを)"
  - "サブクラス化, Windows コントロール"
ms.assetid: 3236d4de-401f-49b7-918d-c84559ecc426
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MFC ActiveX コントロール : Windows コントロールのサブクラス化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ActiveX コントロールを作成するための共通の Windows コントロールをサブクラス化するためのプロセスについて説明します。  既存のウィンドウのコントロールをサブクラス化すると、ActiveX コントロールの開発方法が簡単です。  新しいコントロールに描画やマウスのクリックに応答するようにサブクラス化された Windows フォーム コントロールの機能があります。  MFC ActiveX コントロール [ボタン](../top/visual-cpp-samples.md) サンプルでは、Windows フォーム コントロールをサブクラス化する例です。  
  
 Windows コントロールをサブクラス化するには、次のタスクを実行する:  
  
-   [COleControl の IsSubclassedControl と PreCreateWindow のメンバー関数をオーバーライドします。](#_core_overriding_issubclassedcontrol_and_precreatewindow)  
  
-   [OnDraw メンバー関数を変更します。](#_core_modifying_the_ondraw_member_function)  
  
-   [コントロールが反映された ActiveX コントロール \(OCM\) メッセージを処理してください。](#_core_handling_reflected_window_messages)  
  
    > [!NOTE]
    >  この作業では、ActiveX コントロール ウィザードによって、コントロールを **コントロールの設定** ページの **Select Parent Window Class** のドロップダウン リストを使用してサブクラス化されるように設定した場合に発生します。  
  
 コントロールをサブクラス化する方法の詳細については、サポート技術情報の文書 Q243454 を参照してください。  
  
##  <a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a> オーバーライドの IsSubclassedControl と PreCreateWindow  
 `PreCreateWindow` と `IsSubclassedControl`をオーバーライドするには、コントロールのクラス宣言の `protected` セクションに次のコード行を追加する:  
  
 [!code-cpp[NVC_MFC_AxSub#1](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_1.h)]  
  
 コントロールの実装ファイル \(.cpp\) では、2 種類のオーバーライドされた関数を実装するには、次のコード行を追加する:  
  
 [!code-cpp[NVC_MFC_AxSub#2](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]  
  
 \(この例では、Windows の Button コントロールを `PreCreateWindow`で指定されていることに注意してください。  ただし、標準のコントロールがサブクラス化することができます。  標準のコントロールの詳細については、「[コントロール](../mfc/controls-mfc.md)」を参照してください。  
  
 サブクラス化するときに Windows コントロール、コントロールのウィンドウの作成に使用される特定のウィンドウのスタイル \(**WS\_**\) または拡張ウィンドウ スタイル \(**WS\_EX\_**\) フラグを指定することもできます。  **cs.style** と **cs.dwExStyle** 構造体フィールドを変更して `PreCreateWindow` のメンバー関数のパラメーターの値を設定できます。  これらのフィールドの変更は `OR` 操作を使用してクラス `COleControl`によって設定された既定のフラグを維持するために行う必要があります。  たとえば、コントロールがボタン コントロールをサブクラス化し、コントロールにチェック ボックスとして表示する場合は、return ステートメントの前に `CSampleCtrl::PreCreateWindow`の実装に次のコード行を挿入する:  
  
 [!code-cpp[NVC_MFC_AxSub#3](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]  
  
 この操作は、クラス `COleControl` の既定のスタイル フラグ \(**WS\_CHILD**\) をそのまま中 **BS\_CHECKBOX** のスタイル フラグが追加されます。  
  
##  <a name="_core_modifying_the_ondraw_member_function"></a> OnDraw メンバー関数の変更  
 サブクラス化されたコントロールに対応 `DoSuperclassPaint` がメンバー関数に Windows のコントロール、コントロールの `OnDraw` のメンバー関数呼び出しのみを含める必要があると同じ外観を保持する場合、次の例のように:  
  
 [!code-cpp[NVC_MFC_AxSub#4](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]  
  
 `COleControl`によって実装される `DoSuperclassPaint` のメンバー関数は、外接する四角形内に指定されたデバイス コンテキストのコントロールを描画するために、Windows のコントロールのウィンドウ プロシージャを使用します。  これがアクティブでないときでも、コントロールが表示されるようにします。  
  
> [!NOTE]
>  `DoSuperclassPaint` のメンバー関数は、デバイス コンテキストが `WM_PAINT` メッセージの **wParam** として渡すことができるようにする、コントロール型でのみ使用できます。  これは、Windows の標準コントロールの一部と **SCROLLBAR** と **ボタン**など、すべてのコモン コントロールが含まれます。  この動作をサポートしないコントロールにおいて、適切にアクティブでないコントロールを表示するには、独自のコードを記述する必要があります。  
  
##  <a name="_core_handling_reflected_window_messages"></a> 反射したウィンドウ メッセージの処理  
 Windows のコントロールが親ウィンドウには、通常、一部のウィンドウ メッセージを送信します。  これらのメッセージの一部は、**WM\_COMMAND**など、ユーザーによっては、操作が通知されます。  他のユーザーが、`WM_CTLCOLOR`など、親ウィンドウの情報を取得するために使用されます。  ActiveX コントロールは、通常、他の手段によって親ウィンドウと通信します。  通知は、イベントによって \(イベント通知を送信伝えられ\)、コントロール コンテナーに関する情報はコンテナーのアンビエント プロパティにアクセスします。  これらの通信の手法があるコントロールから送信されたウィンドウ メッセージを処理すると、ActiveX コントロール コンテナーは要求されません。  
  
 コンテナーがコントロールの親コントロールとして動作するようにサブクラス化された Windows コントロールから送られたウィンドウ メッセージを受け取ることが `COleControl` が作成する追加ウィンドウができないようにします。  「リフレクターと呼ばれるこの余分なウィンドウは、Windows コントロールをサブクラス化し、コントロール ウィンドウと同じサイズと位置を持つ ActiveX コントロールに対して」を使って作成されます。  リフレクタ ウィンドウは特定のウィンドウ メッセージを受け取り、コントロールに返します。  コントロールは、ウィンドウ プロシージャの ActiveX コントロールの適切なアクションを実行すると、これらのリフレクション メッセージを処理できます \(たとえば、イベントを発生させます。  受け取られたメッセージ ウィンドウと対応するリフレクション メッセージの一覧の [反射したウィンドウ メッセージ ID](../mfc/reflected-window-message-ids.md) を参照してください。  
  
 ActiveX コントロール コンテナーはメッセージ リフレクション自体を実行することもできます。`COleControl` の必要性がリフレクタ ウィンドウを作成し、削除するサブクラス化された Windows のコントロールの実行時のオーバーヘッドが減少します。  `COleControl` は **TRUE**の値で MessageReflect のアンビエント プロパティをチェックし、かどうかコンテナー サポートこの機能が検出されます。  
  
 反映されたウィンドウ メッセージを処理するには、エントリを制御メッセージ マップに追加し、ハンドラー関数を実装してください。  リフレクション メッセージが Windows で定義されているメッセージの標準セットに含まれないため、クラス ビューでは、このようなメッセージ ハンドラーの追加をサポートしません。  ただし、ハンドラーを手動で追加することは困難です。  
  
 反射したウィンドウ メッセージのメッセージ ハンドラーを追加するには、手動で次のようにする:  
  
-   コントロール クラス。H ファイルは、ハンドラー関数を宣言します。  関数は、それぞれ **LRESULT** と 2 個のパラメーターの戻り値の型が、その型 **WPARAM** と **LPARAM**である必要があります。  たとえば、次のようになります。  
  
     [!code-cpp[NVC_MFC_AxSub#5](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_5.h)]  
    [!code-cpp[NVC_MFC_AxSub#6](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_6.h)]  
  
-   コントロール クラス .cpp ファイルで、`ON_MESSAGE` メッセージ マップにエントリを追加します。  このエントリのパラメーターはハンドラー関数のメッセージ ID と名前。  たとえば、次のようになります。  
  
     [!code-cpp[NVC_MFC_AxSub#7](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]  
  
-   、.cpp ファイルで、リフレクション メッセージを処理するために **OnOcmCommand** メンバー関数を実装してください。  **wParam** と **lParam** パラメーターは元のウィンドウ メッセージと同じです。  
  
 例については、"リフレクション メッセージがどのように処理されるか、MFC ActiveX コントロール [ボタン](../top/visual-cpp-samples.md)サンプルを参照してください。  これは **BN\_CLICKED** 通知コードを検出し、送信 \(\) によって発生 Click イベントに応答 **OnOcmCommand** ハンドラーを示します。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)