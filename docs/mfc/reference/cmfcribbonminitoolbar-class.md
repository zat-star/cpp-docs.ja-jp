---
title: "CMFCRibbonMiniToolBar クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonMiniToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonMiniToolBar クラス"
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCRibbonMiniToolBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンテキスト ポップアップ ツール バーを実装します。  
  
## 構文  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|既定のコンストラクターです。|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|`CMFCRibbonMiniToolBar::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCRibbonMiniToolBar::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するためにフレームワークで使用されます。|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](../Topic/CMFCRibbonMiniToolBar::IsContextMenuMode.md)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](../Topic/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar.md)|\(`CMFCPopupMenu::IsRibbonMiniToolBar` をオーバーライドします\)。|  
|[CMFCRibbonMiniToolBar::SetCommands](../Topic/CMFCRibbonMiniToolBar::SetCommands.md)|ツール バーに表示するコマンドのリストを設定します。|  
|[CMFCRibbonMiniToolBar::Show](../Topic/CMFCRibbonMiniToolBar::Show.md)|指定した画面座標に、ミニ ツール バーを表示します。|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](../Topic/CMFCRibbonMiniToolBar::ShowWithContextMenu.md)|コンテキスト メニューとミニ ツール バーが表示されます。|  
  
## 解説  
 ミニ ツール バーは、通常、ユーザーがドキュメント内のオブジェクトを選択した後に表示されます。  たとえば、ユーザーがワード プロセッサ プログラム内のテキストを選択すると、アプリケーションでテキストの書式設定コマンドを含むミニ ツール バーが表示されます。  
  
 マウス ポインターがミニ ツール バーの境界外にあるときは、ミニ ツール バーは透明になります。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../Topic/CMFCPopupMenu%20Class.md)  
  
 `CMFCRibbonPanelMenu`  
  
 [CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)  
  
## 必要条件  
 **ヘッダー:** afxRibbonMiniToolBar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)