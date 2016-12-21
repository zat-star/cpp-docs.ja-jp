---
title: "CMFCDesktopAlertWnd クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDesktopAlertWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWnd クラス"
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDesktopAlertWnd クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCDesktopAlertWnd` クラスは、画面に表示されてユーザーにイベントについて通知するモードレス ダイアログ ボックスの機能を実装します。  
  
## 構文  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md)|デスクトップ通知ウィンドウを作成し、初期化します。|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::GetAnimationSpeed.md)|アニメーション速度を返します。|  
|[CMFCDesktopAlertWnd::GetAnimationType](../Topic/CMFCDesktopAlertWnd::GetAnimationType.md)|アニメーションの種類を返します。|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](../Topic/CMFCDesktopAlertWnd::GetAutoCloseTime.md)|自動終了のタイムアウトを返します。|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](../Topic/CMFCDesktopAlertWnd::GetCaptionHeight.md)|キャプションの高さを返します。|  
|[CMFCDesktopAlertWnd::GetDialogSize](../Topic/CMFCDesktopAlertWnd::GetDialogSize.md)||  
|[CMFCDesktopAlertWnd::GetLastPos](../Topic/CMFCDesktopAlertWnd::GetLastPos.md)|画面上のデスクトップ通知ウィンドウの最後の有効な位置を返します。|  
|[CMFCDesktopAlertWnd::GetTransparency](../Topic/CMFCDesktopAlertWnd::GetTransparency.md)|透明度レベルを返します。|  
|[CMFCDesktopAlertWnd::HasSmallCaption](../Topic/CMFCDesktopAlertWnd::HasSmallCaption.md)|デスクトップ通知ウィンドウに小さいキャプションが表示されているかどうかを判断します。|  
|[CMFCDesktopAlertWnd::OnBeforeShow](../Topic/CMFCDesktopAlertWnd::OnBeforeShow.md)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](../Topic/CMFCDesktopAlertWnd::OnClickLinkButton.md)|ユーザーがデスクトップ通知メニュー上のリンク ボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CMFCDesktopAlertWnd::OnCommand](../Topic/CMFCDesktopAlertWnd::OnCommand.md)|このメンバー関数は、ユーザーがメニューの項目を選択したとき、子コントロールから通知メッセージが送られたとき、またはアクセラレータのキーストロークが変換されたときに、フレームワークによって呼び出されます   \([CWnd::OnCommand](../Topic/CWnd::OnCommand.md) をオーバーライドします\)。|  
|[CMFCDesktopAlertWnd::OnDraw](../Topic/CMFCDesktopAlertWnd::OnDraw.md)||  
|[CMFCDesktopAlertWnd::ProcessCommand](../Topic/CMFCDesktopAlertWnd::ProcessCommand.md)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::SetAnimationSpeed.md)|新しいアニメーション速度を設定します。|  
|[CMFCDesktopAlertWnd::SetAnimationType](../Topic/CMFCDesktopAlertWnd::SetAnimationType.md)|アニメーションの種類を設定します。|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](../Topic/CMFCDesktopAlertWnd::SetAutoCloseTime.md)|自動終了のタイムアウトを設定します。|  
|[CMFCDesktopAlertWnd::SetSmallCaption](../Topic/CMFCDesktopAlertWnd::SetSmallCaption.md)|小さいキャプションと標準のキャプションとを切り替えます。|  
|[CMFCDesktopAlertWnd::SetTransparency](../Topic/CMFCDesktopAlertWnd::SetTransparency.md)|透明度レベルを設定します。|  
  
## 解説  
 デスクトップ通知ウィンドウは、透明にすることも、アニメーション効果を使用することも、また、非表示にもできます \(指定された遅延時間の経過後、またはユーザーが閉じるボタンをクリックして閉じたとき\)。  
  
 デスクトップ通知ウィンドウには既定のダイアログ ボックスを含めることができ、そのダイアログ ボックスにはアイコン、メッセージ テキスト \(ラベル\)、およびリンクを含めることができます。  または、デスクトップ通知ウィンドウで、アプリケーションのリソースからカスタム ダイアログ ボックスを含めることができます。  
  
 デスクトップ通知ウィンドウは次の手順で作成されます。  まず、コンストラクターを呼び出して `CMFCDesktopAlertWnd` オブジェクトを構築します。  次に、[CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) メンバー関数を呼び出してウィンドウを作成し、それを `CMFCDesktopAlertWnd` オブジェクトに結び付けます。  
  
 `CMFCDesktopAlertWnd` オブジェクトは、デスクトップ通知ウィンドウのクライアント領域全体を占める専用の子ダイアログ ボックスを作成します。  このダイアログ ボックスは、その上にあるすべてのコントロールを所有します。  
  
 ポップアップ ウィンドウにカスタム ダイアログ ボックスを表示するには、次の手順に従います。  
  
1.  `CMFCDesktopAlertDialog` の派生クラスを作成します。  
  
2.  リソースに子ダイアログ ボックスのテンプレートを作成します。  
  
3.  ダイアログ ボックスのテンプレートのリソース ID と、派生クラスのランタイム クラス情報へのポインターを使用して、[CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) を呼び出します。  
  
4.  ホストされているコントロールからのすべての通知を処理するカスタム ダイアログ ボックスをプログラムするか、ホストされているコントロールですべての通知を直接処理するようプログラムします。  
  
 デスクトップ通知ウィンドウの動作を制御するには、次の関数を使用します。  
  
-   アニメーションの種類を設定するには、[CMFCDesktopAlertWnd::SetAnimationType](../Topic/CMFCDesktopAlertWnd::SetAnimationType.md) を呼び出します。  有効なオプションは展開、スライド、およびフェードです。  
  
-   アニメーションのフレーム速度を設定するには、[CMFCDesktopAlertWnd::SetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::SetAnimationSpeed.md) を呼び出します。  
  
-   透明度レベルを設定するには、[CMFCDesktopAlertWnd::SetTransparency](../Topic/CMFCDesktopAlertWnd::SetTransparency.md) を呼び出します。  
  
-   キャプションのサイズを小さくするには、[CMFCDesktopAlertWnd::SetSmallCaption](../Topic/CMFCDesktopAlertWnd::SetSmallCaption.md) を呼び出します。  小さいキャプションの高さは 7 ピクセルです。  
  
## 使用例  
 `CMFCDesktopAlertWnd` クラスのさまざまなメソッドを使用して `CMFCDesktopAlertWnd` オブジェクトを構成する方法を次の例に示します。  この例では、アニメーションの種類の設定、ポップアップ ウィンドウの透明度の設定、通知ウィンドウで小さいキャプションを表示する指定、および通知ウィンドウが自動的に閉じられるまでの時間の設定方法を示します。  また、デスクトップ通知ウィンドウを作成および初期化する方法も示します。  このコード スニペットは [デスクトップ通知デモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/CPP/cmfcdesktopalertwnd-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## 必要条件  
 **ヘッダー :** afxDesktopAlertWnd.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCDesktopAlertWndInfo クラス](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)