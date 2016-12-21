---
title: "CMFCMenuButton クラス | Microsoft Docs"
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
  - "CMFCMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMenuButton クラス"
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
caps.latest.revision: 32
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCMenuButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ポップアップ メニューを表示してユーザーのメニュー選択を報告するボタンです。  
  
## 構文  
  
```  
class CMFCMenuButton : public CMFCButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCMenuButton::CMFCMenuButton](../Topic/CMFCMenuButton::CMFCMenuButton.md)|`CMFCMenuButton` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCMenuButton::PreTranslateMessage](../Topic/CMFCMenuButton::PreTranslateMessage.md)|ディスパッチする前にウィンドウのメッセージを変換するために、フレームワークによって呼び出されます。  \(`CMFCButton::PreTranslateMessage` をオーバーライドします。\)|  
|[CMFCMenuButton::SizeToContent](../Topic/CMFCMenuButton::SizeToContent.md)|ボタンのテキストとイメージのサイズに合わせてボタンのサイズを変更します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCMenuButton::m\_bOSMenu](../Topic/CMFCMenuButton::m_bOSMenu.md)|既定のシステム ポップアップ メニューを表示するか、[CContextMenuManager::TrackPopupMenu](../Topic/CContextMenuManager::TrackPopupMenu.md) を使用するかを指定します。|  
|[CMFCMenuButton::m\_bRightArrow](../Topic/CMFCMenuButton::m_bRightArrow.md)|ポップアップ メニューをボタンの下に表示するか、右側に表示するかを指定します。|  
|[CMFCMenuButton::m\_bStayPressed](../Topic/CMFCMenuButton::m_bStayPressed.md)|ユーザーがボタンを離したときに、メニュー ボタンの状態を変更するかどうかを指定します。|  
|[CMFCMenuButton::m\_hMenu](../Topic/CMFCMenuButton::m_hMenu.md)|結び付けられた Windows メニューへのハンドル。|  
|[CMFCMenuButton::m\_nMenuResult](../Topic/CMFCMenuButton::m_nMenuResult.md)|ユーザーがポップアップ メニューから選択した項目を示す識別子。|  
  
## 解説  
 `CMFCMenuButton` クラスは、[CButton クラス](../../mfc/reference/cbutton-class.md)から派生した [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)から派生します。  したがって、コードでは `CButton` を使用するのと同じ方法で `CMFCMenuButton` を使用できます。  
  
 `CMFCMenuButton` を作成するときは、関連付けられたポップアップ メニューへのハンドルを渡す必要があります。  次に、`CMFCMenuButton::SizeToContent` 関数を呼び出します。  `CMFCMenuButton::SizeToContent` は、ボタン サイズが、ポップアップ ウィンドウの表示場所 \(つまり、ボタンの下または右側\) を示す矢印を十分に含むことができる大きさであることを確認します。  
  
## 使用例  
 ボタンに結び付けられたメニューのハンドルを設定する方法、テキストとイメージのサイズに従ってボタンのサイズを変更する方法、フレームワークにより表示されるポップアップ メニューを設定する方法を次の例に示します。  このコード スニペットは [新しいコントロールのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_NewControls#38](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#38)]  
[!CODE [NVC_MFC_NewControls#39](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#39)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## 必要条件  
 **ヘッダー :** afxmenubutton.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)