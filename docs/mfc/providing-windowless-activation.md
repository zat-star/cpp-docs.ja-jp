---
title: "ウィンドウなしのアクティベーション | Microsoft Docs"
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
  - "アクティベーション [C++], MFC ActiveX コントロール"
  - "アクティベーション [C++], ウィンドウなしの"
  - "MFC ActiveX コントロール [C++], アクティブ化のオプション"
  - "ウィンドウなしのアクティベーション (MFC ActiveX コントロールの)"
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ウィンドウなしのアクティベーション
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**CreateWindow**を呼び出すときのウィンドウの作成コード \(つまり、すべて\) を実行するために重要です。  画面上のウィンドウを保持するコントロールはウィンドウのメッセージを管理する必要があります。  そのため、ウィンドウなしのコントロールはウィンドウを持つコントロールよりもあります。  
  
 ウィンドウなしのコントロールでそのほかの利点は、ウィンドウのコントロールとは異なり、ウィンドウなしのコントロールが透明レンダリングと四角形画面領域をサポートすることです。  透過的なコントロールの一般的な例は、透明な背景のテキスト コントロールです。  テキスト コントロールは、背景を描画しますが、そのものはすべて、テキスト表示の下にあります。  新しいフォームは、矢印、丸いボタンなど、四角形以外のコントロールを利用します。  
  
 多くの場合、代わりに、コントロールがウィンドウなしのオブジェクトをサポートするコンテナーが記述されている場合は、独自のウィンドウを必要とせず、コンテナー ウィンドウ サービスを使用できません。  ウィンドウなしのコントロールは古いコンテナーと下位互換性があります。  サポート ウィンドウなしのコントロールに書き込まれない古いコンテナーでウィンドウなしのコントロールは時アクティブ ウィンドウを作成します。  
  
 ウィンドウなしのコントロールが独自のウィンドウがないため、\(ウィンドウを持つ\) コンテナー コントロールの独自のウィンドウすることによって提供されたサービスを提供する必要があります。  たとえば、キーボード フォーカスを呼び出すか、マウスをキャプチャするか、デバイス コンテキストを取得する制御ニーズがコンテナーによってこれらの操作管理されます。  コンテナーは `IOleInPlaceObjectWindowless` インターフェイスを使用して適切なウィンドウなしのコントロールへのユーザー入力ウィンドウに送信されるメッセージをルーティングします。\(このインターフェイスの説明の *ActiveX SDK を* 参照してください\)。`COleControl` のメンバー関数コンテナーからこれらのサービスを呼び出す。  
  
 コントロールには、ウィンドウなしのアクティベーションを使用します [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md)によって返されるフラグを設定する **windowlessActivate** フラグを含めます。  たとえば、次のようになります。  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/CPP/providing-windowless-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#6](../mfc/codesnippet/CPP/providing-windowless-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/CPP/providing-windowless-activation_3.cpp)]  
  
 このフラグが含まれるコードは自動的に MFC ActiveX コントロール ウィザードの [コントロールの設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md) ページの **ウィンドウなしでアクティブ\(S\)** オプションを選択すると生成されます。  
  
 ウィンドウなしでアクティブ化が有効になっている場合、コンテナーは、コントロールの `IOleInPlaceObjectWindowless` インターフェイスにメッセージを送信するために委任します。  この インターフェイスの`COleControl` の実装はコントロールのメッセージ マップを通じてマウスの座標を適切に調整すると、メッセージをディスパッチします。  メッセージ マップに対応するエントリを追加することによって、通常のウィンドウ メッセージなどのメッセージを処理できます。  これらのメッセージのハンドラーでは、最初に値が **NULL**でないことを確認するに `m_hWnd` のメンバー変数 \(または、使用するメンバー関数\) を使用しないでください。  
  
 `COleControl` を適切にコンテナーからマウス キャプチャ、キーボード フォーカス、スクロールなどの Windows サービスを呼び出すには、次のようなメンバー関数を提供し、T:  
  
-   [GetFocus](../Topic/COleControl::GetFocus.md)、[SetFocus](../Topic/COleControl::SetFocus.md)  
  
-   [GetCapture](../Topic/COleControl::GetCapture.md)、[SetCapture](../Topic/COleControl::SetCapture.md)、[ReleaseCapture](../Topic/COleControl::ReleaseCapture.md)  
  
-   [GetDC](../Topic/COleControl::GetDC.md)、[ReleaseDC](../Topic/COleControl::ReleaseDC.md)  
  
-   [InvalidateRgn](../Topic/COleControl::InvalidateRgn.md)  
  
-   [ScrollWindow](../Topic/COleControl::ScrollWindow.md)  
  
-   [GetClientRect](../Topic/COleControl::GetClientRect.md)  
  
 ウィンドウなしのコントロールでは、`CWnd` の対応するメンバー関数または関連する Win32 API 関数の代わりに `COleControl` メンバー関数を必ず使用する必要があります。  
  
 ウィンドウなしのコントロールに OLE ドラッグ アンド ドロップ操作のターゲットとすることができます。  通常、コントロールのウィンドウがドロップ ターゲットとして登録されている必要があります。  コントロールが独自のウィンドウがないため、コンテナーはドロップ ターゲットとして独自のウィンドウを使用します。  コントロールがコンテナーが適切なタイミングで呼び出しの処理できる `IDropTarget` インターフェイスの実装を提供します。  コンテナーにこのインターフェイスを公開するには、[COleControl::GetWindowlessDropTarget](../Topic/COleControl::GetWindowlessDropTarget.md)をオーバーライドします。  たとえば、次のようになります。  
  
 [!code-cpp[NVC_MFC_AxOpt#8](../mfc/codesnippet/CPP/providing-windowless-activation_4.cpp)]  
  
## 参照  
 [MFC ActiveX コントロール : 最適化](../mfc/mfc-activex-controls-optimization.md)