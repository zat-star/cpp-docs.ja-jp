---
title: "CMFCStatusBar クラス | Microsoft Docs"
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
  - "CMFCStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCStatusBar クラス"
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
caps.latest.revision: 36
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCStatusBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCStatusBar` クラスは、`CStatusBar` クラスに似たステータス バーを実装します。  ただし、`CMFCStatusBar` クラスには、イメージ、アニメーション、およびプログレス バーを表示する機能や、マウスのダブルクリックに応答する機能など、`CStatusBar` クラスでは提供されない機能が含まれています。  
  
## 構文  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCStatusBar::CalcFixedLayout](../Topic/CMFCStatusBar::CalcFixedLayout.md)|\([CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md) をオーバーライドします。\)|  
|[CMFCStatusBar::CommandToIndex](../Topic/CMFCStatusBar::CommandToIndex.md)||  
|[CMFCStatusBar::Create](../Topic/CMFCStatusBar::Create.md)|コントロール バーを作成し、[CPane](../../mfc/reference/cpane-class.md) オブジェクトにアタッチします。  \([CPane::Create](../Topic/CPane::Create.md) をオーバーライドします。\)|  
|[CMFCStatusBar::CreateEx](../Topic/CMFCStatusBar::CreateEx.md)|コントロール バーを作成し、[CPane](../../mfc/reference/cpane-class.md) オブジェクトにアタッチします。  \([CPane::CreateEx](../Topic/CPane::CreateEx.md) をオーバーライドします。\)|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](../Topic/CMFCStatusBar::DoesAllowDynInsertBefore.md)|別のペインを現在のペインと親フレームの間に動的に挿入できるかどうかを判定します。  \([CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md) をオーバーライドします。\)|  
|[CMFCStatusBar::EnablePaneDoubleClick](../Topic/CMFCStatusBar::EnablePaneDoubleClick.md)|ステータス バーでのマウスのダブルクリックの処理を有効または無効にします。|  
|[CMFCStatusBar::EnablePaneProgressBar](../Topic/CMFCStatusBar::EnablePaneProgressBar.md)|指定したペインにプログレス バーを表示します。|  
|[CMFCStatusBar::GetCount](../Topic/CMFCStatusBar::GetCount.md)|ステータス バーのペインの数を返します。|  
|[CMFCStatusBar::GetDrawExtendedArea](../Topic/CMFCStatusBar::GetDrawExtendedArea.md)||  
|[CMFCStatusBar::GetExtendedArea](../Topic/CMFCStatusBar::GetExtendedArea.md)||  
|[CMFCStatusBar::GetItemID](../Topic/CMFCStatusBar::GetItemID.md)||  
|[CMFCStatusBar::GetItemRect](../Topic/CMFCStatusBar::GetItemRect.md)||  
|[CMFCStatusBar::GetPaneInfo](../Topic/CMFCStatusBar::GetPaneInfo.md)||  
|[CMFCStatusBar::GetPaneProgress](../Topic/CMFCStatusBar::GetPaneProgress.md)||  
|[CMFCStatusBar::GetPaneStyle](../Topic/CMFCStatusBar::GetPaneStyle.md)|ペインのスタイルを返します。  \([CBasePane::GetPaneStyle](../Topic/CBasePane::GetPaneStyle.md) をオーバーライドします。\)|  
|[CMFCStatusBar::GetPaneText](../Topic/CMFCStatusBar::GetPaneText.md)||  
|[CMFCStatusBar::GetPaneWidth](../Topic/CMFCStatusBar::GetPaneWidth.md)|ステータス バーの指定されたペインの幅をピクセル単位で返します。|  
|[CMFCStatusBar::GetTipText](../Topic/CMFCStatusBar::GetTipText.md)|ステータス バーの指定されたペインのツールヒント テキストを返します。|  
|[CMFCStatusBar::InvalidatePaneContent](../Topic/CMFCStatusBar::InvalidatePaneContent.md)|指定されたペインを無効にし、そのコンテンツを再描画します。|  
|[CMFCStatusBar::PreCreateWindow](../Topic/CMFCStatusBar::PreCreateWindow.md)|`CWnd` オブジェクトに結び付けられた Windows のウィンドウが作成される前に、フレームワークから呼び出されます。  \([CWnd::PreCreateWindow](../Topic/CWnd::PreCreateWindow.md) をオーバーライドします。\)|  
|[CMFCStatusBar::SetDrawExtendedArea](../Topic/CMFCStatusBar::SetDrawExtendedArea.md)||  
|[CMFCStatusBar::SetIndicators](../Topic/CMFCStatusBar::SetIndicators.md)||  
|[CMFCStatusBar::SetPaneAnimation](../Topic/CMFCStatusBar::SetPaneAnimation.md)|指定したペインにアニメーションを割り当てます。|  
|[CMFCStatusBar::SetPaneBackgroundColor](../Topic/CMFCStatusBar::SetPaneBackgroundColor.md)|ステータス バーの指定されたペインに背景色を設定します。|  
|[CMFCStatusBar::SetPaneIcon](../Topic/CMFCStatusBar::SetPaneIcon.md)|ステータス バーの指定されたペインにインジケーター アイコンを設定します。|  
|[CMFCStatusBar::SetPaneInfo](../Topic/CMFCStatusBar::SetPaneInfo.md)||  
|[CMFCStatusBar::SetPaneProgress](../Topic/CMFCStatusBar::SetPaneProgress.md)|ステータス バーの指定されたペインに、プログレス バーの現在のプログレスを設定します。|  
|[CMFCStatusBar::SetPaneStyle](../Topic/CMFCStatusBar::SetPaneStyle.md)|ペインのスタイルを設定します。  \([CBasePane::SetPaneStyle](../Topic/CBasePane::SetPaneStyle.md) をオーバーライドします。\)|  
|[CMFCStatusBar::SetPaneText](../Topic/CMFCStatusBar::SetPaneText.md)||  
|[CMFCStatusBar::SetPaneTextColor](../Topic/CMFCStatusBar::SetPaneTextColor.md)|ステータス バーの指定されたペインにテキストの色を設定します。|  
|[CMFCStatusBar::SetPaneWidth](../Topic/CMFCStatusBar::SetPaneWidth.md)|ステータス バーの指定されたペインの幅をピクセル単位で設定します。|  
|[CMFCStatusBar::SetTipText](../Topic/CMFCStatusBar::SetTipText.md)|ステータス バーの指定されたペインにツールヒント テキストを設定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCStatusBar::OnDrawPane](../Topic/CMFCStatusBar::OnDrawPane.md)|ステータス バーにペインを再描画するときにフレームワークによって呼び出されます。|  
  
## 解説  
 次の図は [ステータス バーのデモのサンプル](../../top/visual-cpp-samples.md) のアプリケーションのステータス バーの図を示します。  
  
 ![CMFCStatusBar の例](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar")  
  
## 使用例  
 `CMFCStatusBar` クラスでさまざまなメソッドを呼び出すためにアプリケーションが使用するローカル変数を次の例に示します。  これらの変数は、StatusBarDemoView.h で宣言されています。  メイン フレームは MainFrm.h で宣言され、ドキュメントは StatusBarDemoDoc.h で宣言され、ビューは StatusBarDemoView.h で宣言されています。  このコード スニペットは [ステータス バーのデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_1.h)]  
  
## 使用例  
 MainFrm.h に `GetStatusBar` メソッドを導入し、このメソッドを StatusBarDemoView.h の `GetStatusBar` メソッドから呼び出すことによって、`CMFCStatusBar` オブジェクトへの参照を取得する方法を次の例に示します。  このコード スニペットは [ステータス バーのデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_2.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_3.h)]  
  
## 使用例  
 StatusBarDemoView.cpp の `CMFCStatusBar` クラスでさまざまなメソッドを呼び出す方法を次の例に示します。  定数は MainFrm.h で宣言されます。  この例では、アイコンを設定し、ステータス バー ペインのツールヒント テキストを設定し、指定されたペインにプログレス バーを表示し、指定されたペインにアニメーションを割り当て、ステータス バー ペインのテキストと幅を設定し、ステータス バー ペインにプログレス バーの現在のプログレス インジケーターを設定する方法を示します。  このコード スニペットは [ステータス バーのデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_4.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_5.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_6.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_7.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_8.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_9.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## 必要条件  
 **ヘッダー :** afxstatusbar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CPane クラス](../../mfc/reference/cpane-class.md)   
 [CStatusBar クラス](../../mfc/reference/cstatusbar-class.md)