---
title: "CMFCCaptionBar クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCCaptionBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCaptionBar クラス"
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCCaptionBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCCaptionBar` オブジェクトは、ボタン、テキスト ラベル、ビットマップという 3 つの要素を表示できるコントロール バーです。  表示できる各要素の数は 1 つずつです。  各要素は、コントロールの左端、右端、または中央に揃えて配置できます。  また、キャプション バーの上部または下部の境界線にフラット スタイルまたは 3D スタイルを適用することもできます。  
  
## 構文  
  
```  
class CMFCCaptionBar : public CPane  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md)|キャプション バー コントロールを作成し、`CMFCCaptionBar`のオブジェクトにアタッチします。|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](../Topic/CMFCCaptionBar::DoesAllowDynInsertBefore.md)|別のペインをキャプション バーと親フレームの間に動的に挿入できるかどうかを示します。  \([CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md) をオーバーライドします。\)|  
|[CMFCCaptionBar::EnableButton](../Topic/CMFCCaptionBar::EnableButton.md)|キャプション バーのボタンの有効と無効を切り替えます。|  
|[CMFCCaptionBar::GetAlignment](../Topic/CMFCCaptionBar::GetAlignment.md)|指定した要素の配置を返します。|  
|[CMFCCaptionBar::GetBorderSize](../Topic/CMFCCaptionBar::GetBorderSize.md)|キャプション バーの境界線のサイズを返します。|  
|[CMFCCaptionBar::GetButtonRect](../Topic/CMFCCaptionBar::GetButtonRect.md)|キャプション バーのボタンに外接する四角形を取得します。|  
|[CMFCCaptionBar::GetMargin](../Topic/CMFCCaptionBar::GetMargin.md)|キャプション バー要素の端からキャプション バー コントロールの端までの距離を返します。|  
|[CMFCCaptionBar::IsMessageBarMode](../Topic/CMFCCaptionBar::IsMessageBarMode.md)|キャプション バーがメッセージ バー モードになっているかどうかを示します。|  
|[CMFCCaptionBar::RemoveBitmap](../Topic/CMFCCaptionBar::RemoveBitmap.md)|キャプション バーのビットマップ イメージを削除します。|  
|[CMFCCaptionBar::RemoveButton](../Topic/CMFCCaptionBar::RemoveButton.md)|キャプション バーのボタンを削除します。|  
|[CMFCCaptionBar::RemoveIcon](../Topic/CMFCCaptionBar::RemoveIcon.md)|キャプション バーのアイコンを削除します。|  
|[CMFCCaptionBar::RemoveText](../Topic/CMFCCaptionBar::RemoveText.md)|キャプション バーからテキスト ラベルを削除します。|  
|[CMFCCaptionBar::SetBitmap](../Topic/CMFCCaptionBar::SetBitmap.md)|キャプション バーのビットマップ イメージを設定します。|  
|[CMFCCaptionBar::SetBorderSize](../Topic/CMFCCaptionBar::SetBorderSize.md)|キャプション バーの境界線のサイズを設定します。|  
|[CMFCCaptionBar::SetButton](../Topic/CMFCCaptionBar::SetButton.md)|キャプション バーのボタンを設定します。|  
|[CMFCCaptionBar::SetButtonPressed](../Topic/CMFCCaptionBar::SetButtonPressed.md)|ボタンを押されたままの状態にするかどうかを指定します。|  
|[CMFCCaptionBar::SetButtonToolTip](../Topic/CMFCCaptionBar::SetButtonToolTip.md)|ボタンのツールヒントを設定します。|  
|[CMFCCaptionBar::SetFlatBorder](../Topic/CMFCCaptionBar::SetFlatBorder.md)|キャプション バーの境界線スタイルを設定します。|  
|[CMFCCaptionBar::SetIcon](../Topic/CMFCCaptionBar::SetIcon.md)|キャプション バーのアイコンを設定します。|  
|[CMFCCaptionBar::SetImageToolTip](../Topic/CMFCCaptionBar::SetImageToolTip.md)|キャプション バーのイメージのツールヒントを設定します。|  
|[CMFCCaptionBar::SetMargin](../Topic/CMFCCaptionBar::SetMargin.md)|キャプション バー要素の端からキャプション バー コントロールの端までの距離を設定します。|  
|[CMFCCaptionBar::SetText](../Topic/CMFCCaptionBar::SetText.md)|キャプション バーのテキスト ラベルを設定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCCaptionBar::OnDrawBackground](../Topic/CMFCCaptionBar::OnDrawBackground.md)|キャプション バーの背景を塗りつぶすために、フレームワークによって呼び出されます。|  
|[CMFCCaptionBar::OnDrawBorder](../Topic/CMFCCaptionBar::OnDrawBorder.md)|キャプション バーの境界線を描画するために、フレームワークによって呼び出されます。|  
|[CMFCCaptionBar::OnDrawButton](../Topic/CMFCCaptionBar::OnDrawButton.md)|キャプション バーのボタンを描画するために、フレームワークによって呼び出されます。|  
|[CMFCCaptionBar::OnDrawImage](../Topic/CMFCCaptionBar::OnDrawImage.md)|キャプション バーのイメージを描画するために、フレームワークによって呼び出されます。|  
|[CMFCCaptionBar::OnDrawText](../Topic/CMFCCaptionBar::OnDrawText.md)|キャプション バーのテキストを描画するために、フレームワークによって呼び出されます。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCCaptionBar::m\_clrBarBackground](../Topic/CMFCCaptionBar::m_clrBarBackground.md)|キャプション バーの背景色。|  
|[CMFCCaptionBar::m\_clrBarBorder](../Topic/CMFCCaptionBar::m_clrBarBorder.md)|キャプション バーの境界線の色。|  
|[CMFCCaptionBar::m\_clrBarText](../Topic/CMFCCaptionBar::m_clrBarText.md)|キャプション バー テキストの色。|  
  
## 解説  
 キャプション バーは次の手順で作成します。  
  
1.  `CMFCCaptionBar` オブジェクトを構築します。  一般に、キャプション バーはフレーム ウィンドウ クラスに追加します。  
  
2.  [CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md) メソッドを使用してキャプション バー コントロールを作成し、それを `CMFCCaptionBar` オブジェクトに結び付けます。  
  
3.  キャプション バー要素を設定するには、[CMFCCaptionBar::SetButton](../Topic/CMFCCaptionBar::SetButton.md)、[CMFCCaptionBar::SetText](../Topic/CMFCCaptionBar::SetText.md)、[CMFCCaptionBar::SetIcon](../Topic/CMFCCaptionBar::SetIcon.md)、および [CMFCCaptionBar::SetBitmap](../Topic/CMFCCaptionBar::SetBitmap.md) を呼び出します。  
  
 ボタン要素を設定する場合は、ボタンにコマンド ID を割り当てる必要があります。  ユーザーがボタンをクリックすると、キャプション バーは、この ID を持つ `WM_COMMAND` メッセージを親フレーム ウィンドウに転送します。  
  
 キャプション バーは、メッセージ バー モードでも機能します。このモードは、Microsoft Office 2007 アプリケーションに表示されるメッセージ バーをエミュレートします。  メッセージ バー モードのキャプション バーは、ビットマップ、メッセージ、およびボタン \(一般的にはダイアログ ボックスを開く\) を 1 つずつ表示します。ビットマップにはツールヒントを割り当てることもできます。  
  
 メッセージ バー モードを有効にするには、[CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md) を呼び出し、4 番目のパラメーター \(bIsMessageBarMode\) を `TRUE` に設定します。  
  
## 使用例  
 次の例は、`CMFCCaptionBar` クラスのさまざまなメソッドの使用方法を説明しています。  この例では、キャプション バー コントロールの作成、キャプション バーへの 3D 境界線の設定、キャプション バー要素の端とキャプション バー コントロールの端との距離 \(ピクセル単位\) の設定、キャプション バーのボタンの設定、ボタンのツールヒントの設定、キャプション バーのテキスト ラベルの設定、キャプション バーのテキスト ラベルの設定、およびキャプション バーに含まれるイメージのツールヒントの設定の各手順を示しています。  このコード スニペットは [MS Office 2007 のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_MSOffice2007Demo#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#1)]  
[!CODE [NVC_MFC_MSOffice2007Demo#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#2)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## 必要条件  
 **ヘッダー :** afxcaptionbar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)