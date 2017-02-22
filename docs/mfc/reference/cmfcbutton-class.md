---
title: "CMFCButton クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCButton クラス"
  - "CMFCButton コンストラクター"
  - "CMFCButton::CreateObject メソッド"
  - "CMFCButton::DrawItem メソッド"
  - "CMFCButton::OnDrawParentBackground メソッド"
  - "CMFCButton::PreTranslateMessage メソッド"
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCButton` クラスは、ボタン テキストの整列、ボタン テキストとイメージの組み合わせ、カーソルの選択、ツールヒントの指定などの機能を [CButton](../../mfc/reference/cbutton-class.md) クラスに追加します。  
  
## 構文  
  
```  
class CMFCButton : public CButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCButton::CMFCButton`|既定のコンストラクターです。|  
|`CMFCButton::~CMFCButton`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCButton::CleanUp](../Topic/CMFCButton::CleanUp.md)|内部変数をリセットし、イメージ、ビットマップ、アイコンなどの、割り当てられているリソースを解放します。|  
|`CMFCButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|`CMFCButton::DrawItem`|オーナー描画ボタンの表示上の外観が変化すると、フレームワークが呼び出します   \([CButton::DrawItem](../Topic/CButton::DrawItem.md) をオーバーライドします\)。|  
|[CMFCButton::EnableFullTextTooltip](../Topic/CMFCButton::EnableFullTextTooltip.md)|大きいツールヒント ウィンドウにツールヒントのテキスト全体を表示するか、小さいツールヒント ウィンドウに切り詰められたテキストを表示するかを指定します。|  
|[CMFCButton::EnableMenuFont](../Topic/CMFCButton::EnableMenuFont.md)|ボタン テキストのフォントがアプリケーション メニューのフォントと同じかどうかを指定します。|  
|[CMFCButton::EnableWindowsTheming](../Topic/CMFCButton::EnableWindowsTheming.md)|ボタンの境界線のスタイルを現在の Windows テーマと一致させるかどうかを指定します。|  
|`CMFCButton::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCButton::GetToolTipCtrl](../Topic/CMFCButton::GetToolTipCtrl.md)|基になるツールヒント コントロールへの参照を返します。|  
|[CMFCButton::IsAutoCheck](../Topic/CMFCButton::IsAutoCheck.md)|チェック ボックスまたはオプション ボタンが自動ボタンかどうかを示します。|  
|[CMFCButton::IsAutorepeatCommandMode](../Topic/CMFCButton::IsAutorepeatCommandMode.md)|ボタンが自動繰り返しモードに設定されているかどうかを示します。|  
|[CMFCButton::IsCheckBox](../Topic/CMFCButton::IsCheckBox.md)|ボタンがチェック ボックス ボタンかどうかを示します。|  
|[CMFCButton::IsChecked](../Topic/CMFCButton::IsChecked.md)|現在のボタンがオンになっているかどうかを示します。|  
|[CMFCButton::IsHighlighted](../Topic/CMFCButton::IsHighlighted.md)|ボタンが強調表示されているかどうかを示します。|  
|[CMFCButton::IsPressed](../Topic/CMFCButton::IsPressed.md)|ボタンが押され、強調表示されているかどうかを示します。|  
|[CMFCButton::IsPushed](../Topic/CMFCButton::IsPushed.md)|ボタンがクリックされているかどうかを示します。|  
|[CMFCButton::IsRadioButton](../Topic/CMFCButton::IsRadioButton.md)|ボタンがオプション ボタンかどうかを示します。|  
|[CMFCButton::IsWindowsThemingEnabled](../Topic/CMFCButton::IsWindowsThemingEnabled.md)|ボタンの境界線のスタイルを現在の Windows テーマと一致させるかどうかを示します。|  
|`CMFCButton::OnDrawParentBackground`|指定領域にボタンの親の背景を描画します   \([AFX\_GLOBAL\_DATA::DrawParentBackground](../Topic/AFX_GLOBAL_DATA::DrawParentBackground.md) をオーバーライドします\)。|  
|`CMFCButton::PreTranslateMessage`|Windows 関数の [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) や [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) にディスパッチする前にウィンドウ メッセージを変換します。  \([CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md) をオーバーライドします\)。|  
|[CMFCButton::SetAutorepeatMode](../Topic/CMFCButton::SetAutorepeatMode.md)|ボタンをオートリピート モードに設定します。|  
|[CMFCButton::SetCheckedImage](../Topic/CMFCButton::SetCheckedImage.md)|オン状態のボタンのイメージを設定します。|  
|[CMFCButton::SetFaceColor](../Topic/CMFCButton::SetFaceColor.md)|ボタン テキストの背景色を設定します。|  
|[CMFCButton::SetImage](../Topic/CMFCButton::SetImage.md)|ボタンのイメージを設定します。|  
|[CMFCButton::SetMouseCursor](../Topic/CMFCButton::SetMouseCursor.md)|カーソル イメージを設定します。|  
|[CMFCButton::SetMouseCursorHand](../Topic/CMFCButton::SetMouseCursorHand.md)|カーソルを手の形のカーソルのイメージに設定します。|  
|[CMFCButton::SetStdImage](../Topic/CMFCButton::SetStdImage.md)|`CMenuImages` のオブジェクトをボタンのイメージを設定します。|  
|[CMFCButton::SetTextColor](../Topic/CMFCButton::SetTextColor.md)|選択されていないボタンのボタン テキストの色を設定します。|  
|[CMFCButton::SetTextHotColor](../Topic/CMFCButton::SetTextHotColor.md)|選択されているボタンのボタン テキストの色を設定します。|  
|[CMFCButton::SetTooltip](../Topic/CMFCButton::SetTooltip.md)|ツールヒントをボタンに関連付けます。|  
|[CMFCButton::SizeToContent](../Topic/CMFCButton::SizeToContent.md)|ボタン テキストおよびイメージを格納するボタンのサイズを変更します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCButton::OnDraw](../Topic/CMFCButton::OnDraw.md)|ボタンを描画するために、フレームワークが呼び出します。|  
|[CMFCButton::OnDrawBorder](../Topic/CMFCButton::OnDrawBorder.md)|ボタンの境界線を描画するために、フレームワークによって呼び出されます。|  
|[CMFCButton::OnDrawFocusRect](../Topic/CMFCButton::OnDrawFocusRect.md)|ボタンのフォーカスを示す四角形を描画するために、フレームワークによって呼び出されます。|  
|[CMFCButton::OnDrawText](../Topic/CMFCButton::OnDrawText.md)|ボタン テキストを描画するために、フレームワークによって呼び出されます。|  
|[CMFCButton::OnFillBackground](../Topic/CMFCButton::OnFillBackground.md)|ボタン テキストの背景を描画するために、フレームワークによって呼び出されます。|  
|[CMFCButton::SelectFont](../Topic/CMFCButton::SelectFont.md)|指定されたデバイス コンテキストに関連付けられているフォントを取得します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCButton::m\_bDrawFocus](../Topic/CMFCButton::m_bDrawFocus.md)|ボタンの周囲にフォーカスを示す四角形を描画するかどうかを指定します。|  
|[CMFCButton::m\_bHighlightChecked](../Topic/CMFCButton::m_bHighlightChecked.md)|BS\_CHECKBOX スタイルのボタンの上にカーソルが置かれたときに、そのボタンを強調表示するかどうかを指定します。|  
|[CMFCButton::m\_bRightImage](../Topic/CMFCButton::m_bRightImage.md)|ボタンの右側にイメージを表示するかどうかを指定します。|  
|[CMFCButton::m\_bTransparent](../Topic/CMFCButton::m_bTransparent.md)|ボタンが透明かどうかを示します。|  
|[CMFCButton::m\_nAlignStyle](../Topic/CMFCButton::m_nAlignStyle.md)|ボタン テキストの配置を指定します。|  
|[CMFCButton::m\_nFlatStyle](../Topic/CMFCButton::m_nFlatStyle.md)|ボーダーレス、フラット、セミフラット、3D などの、ボタンのスタイルを指定します。|  
  
## 解説  
 他の種類のボタンは、ハイパーリンクをサポートする [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) クラスやカラー ピッカー ダイアログ ボックスをサポートする `CMFCColorButton` クラスなどの `CMFCButton` クラスから派生します。  
  
 `CMFCButton` オブジェクトのスタイルは、*3D*、*フラット*、*セミフラット*、または*境界線なし*となります。  ボタン テキストは、ボタンの左側、上部、または中央に揃えて配置できます。  実行時に、ボタンにテキスト、イメージ、またはテキストとイメージを表示するかどうかを制御できます。  カーソルをボタンの上に置いたときに、特定のカーソル イメージを表示するように指定することもできます。  
  
 ボタン コントロールを、コードで直接作成するか、MFC クラス ウィザード ツールとダイアログ ボックス テンプレートを使用して作成します。  ボタン コントロールを直接作成する場合は、アプリケーションに `CMFCButton` 変数を追加し、`CMFCButton` オブジェクトのコンストラクターおよび `Create` メソッドを呼び出します。  MFC クラス ウィザードを使用する場合は、アプリケーションに `CButton` 変数を追加し、変数の型を `CButton` から `CMFCButton` に変更します。  
  
 ダイアログ ボックス アプリケーションで通知メッセージを処理するには、各通知のメッセージ マップ エントリとイベント ハンドラーを追加します。  `CMFCButton` オブジェクトから送信される通知は、`CButton` オブジェクトから送信される通知と同じです。  
  
## 使用例  
 `CMFCButton` クラスのさまざまなメソッドを使用してボタンのプロパティを設定する方法を次の例に示します。  この例では [新しいコントロールのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_NewControls#28](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#28)]  
[!CODE [NVC_MFC_NewControls#31](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#31)]  
[!CODE [NVC_MFC_NewControls#32](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#32)]  
[!CODE [NVC_MFC_NewControls#33](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#33)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
## 必要条件  
 **ヘッダー :** afxbutton.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCLinkCtrl クラス](../../mfc/reference/cmfclinkctrl-class.md)   
 [CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)   
 [CMFCMenuButton クラス](../../mfc/reference/cmfcmenubutton-class.md)