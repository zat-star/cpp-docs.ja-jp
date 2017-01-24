---
title: "CMouseManager クラス | Microsoft Docs"
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
  - "CMouseManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMouseManager クラス"
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
caps.latest.revision: 26
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMouseManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザーが特定の [CView](../Topic/CView%20Class.md) オブジェクトにおけるビューの内側をダブルクリックしたときに、さまざまなコマンドをそのビューに関連付けられるようにします。  
  
## 構文  
  
```  
class CMouseManager : public CObject  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMouseManager::AddView](../Topic/CMouseManager::AddView.md)|`CView` オブジェクトを **\[カスタマイズ\]** ダイアログ ボックスに追加します。  ユーザーは **\[カスタマイズ\]** ダイアログ ボックスを使用して、リストされている各ビューに対し、ダブルクリックにコマンドを関連付けることができます。|  
|[CMouseManager::GetViewDblClickCommand](../Topic/CMouseManager::GetViewDblClickCommand.md)|表示されているビュー内をユーザーがダブルクリックしたときに実行されるコマンドを返します。|  
|[CMouseManager::GetViewIconId](../Topic/CMouseManager::GetViewIconId.md)|指定されたビュー ID に関連付けられているアイコンを返します。|  
|[CMouseManager::GetViewIdByName](../Topic/CMouseManager::GetViewIdByName.md)|指定されたビュー名に関連付けられているビュー ID を返します。|  
|[CMouseManager::GetViewNames](../Topic/CMouseManager::GetViewNames.md)|追加されているすべてのビュー名の一覧を取得します。|  
|[CMouseManager::LoadState](../Topic/CMouseManager::LoadState.md)|Windows レジストリから `CMouseManager` の状態を読み込みます。|  
|[CMouseManager::SaveState](../Topic/CMouseManager::SaveState.md)|`CMouseManager` の状態を Windows レジストリに書き込みます。|  
|[CMouseManager::SetCommandForDblClk](../Topic/CMouseManager::SetCommandForDblClk.md)|指定されたコマンドと指定されたビューを関連付けます。|  
  
## 解説  
 `CMouseManager` クラスは、`CView` オブジェクトのコレクションを管理します。  各ビューは名前と ID で識別されます。  ビューは **\[カスタマイズ\]** ダイアログ ボックスに表示されます。  ユーザーは **\[カスタマイズ\]** ダイアログ ボックスを使用して、任意のビューに関連付けられているコマンドを変更できます。  関連付けられているコマンドは、ユーザーがビュー内をダブルクリックしたときに実行されます。  この機能をコードの面からサポートするには、`CView` オブジェクト用のコードの中で、`WM_LBUTTONDBLCLK` メッセージを処理して [CWinAppEx::OnViewDoubleClick](../Topic/CWinAppEx::OnViewDoubleClick.md) 関数を呼び出す必要があります。  
  
 `CMouseManager` オブジェクトは手動で作成しないでください。  このオブジェクトは、アプリケーションのフレームワークにより作成されます。  また、ユーザーがアプリケーションを終了すると自動的に破棄されます。  アプリケーションのマウス マネージャーへのポインターを取得するには、[CWinAppEx::GetMouseManager](../Topic/CWinAppEx::GetMouseManager.md) を呼び出します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMouseManager](../../mfc/reference/cmousemanager-class.md)  
  
## 必要条件  
 **ヘッダー :** afxmousemanager.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)   
 [キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)