---
title: "CDialogEx クラス | Microsoft Docs"
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
  - "CDialogEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogEx クラス"
  - "CDialogEx::PreTranslateMessage メソッド"
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
caps.latest.revision: 27
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDialogEx クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDialogEx` クラスは、ダイアログ ボックスの背景色と背景イメージを指定します。  
  
## 構文  
  
```  
class CDialogEx : public CDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDialogEx::CDialogEx](../Topic/CDialogEx::CDialogEx.md)|`CDialogEx` オブジェクトを構築します。|  
|`CDialogEx::~CDialogEx`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDialogEx::SetBackgroundColor](../Topic/CDialogEx::SetBackgroundColor.md)|ダイアログ ボックスの背景色を設定します。|  
|[CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md)|ダイアログ ボックスの背景イメージを設定します。|  
  
## 解説  
 `CDialogEx` クラスを使用するには、ダイアログ ボックス クラスを `CDialogEx` クラスではなく `CDialog` クラスから派生させます。  
  
 ダイアログ ボックス イメージは、リソース ファイルに格納されます。  フレームワークは、リソース ファイルから読み込まれたイメージを自動的に削除します。  現在の背景イメージをプログラムで削除するには、[CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md) メソッドを呼び出すか、`OnDestroy` イベント ハンドラーを実装します。  [CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md) メソッドを呼び出すときには、イメージ ハンドルとして `HBITMAP` パラメーターを渡します。  `CDialogEx` オブジェクトがイメージの所有権を取得し、`m_bAutoDestroyBmp` フラグが `TRUE` である場合は、そのイメージを削除します。  
  
 `CDialogEx` オブジェクトは、[CMFCPopupMenu クラス](../Topic/CMFCPopupMenu%20Class.md) オブジェクトの親になることができます。  [CMFCPopupMenu クラス](../Topic/CMFCPopupMenu%20Class.md) オブジェクトは、[CMFCPopupMenu クラス](../Topic/CMFCPopupMenu%20Class.md) オブジェクトが開いたときに `CDialogEx::SetActiveMenu` メソッドを呼び出します。  その後、`CDialogEx` オブジェクトは、[CMFCPopupMenu クラス](../Topic/CMFCPopupMenu%20Class.md) オブジェクトが閉じられるまで、あらゆるメニュー イベントを処理します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
## 必要条件  
 **ヘッダー :** afxdialogex.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCPopupMenu クラス](../Topic/CMFCPopupMenu%20Class.md)   
 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)