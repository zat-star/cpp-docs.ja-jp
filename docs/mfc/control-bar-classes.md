---
title: "コントロール バー クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コントロール バー, クラス"
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# コントロール バー クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コントロール バーをフレーム ウィンドウに接続されます。  これらは、ボタン、ステータス バー ペインまたはダイアログ テンプレートが含まれています。  ツールのパレット非フローティング コントロール バーは、[CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) オブジェクトへの接続によって実装されます。  
  
## フレームワーク コントロール バー  
 これらのコントロール バーは、MFC フレームワークにとって不可欠な部分です。  これらはフレームワークと統合されているため、使用しやすさ Windows コントロール バーより強力です。  ほとんどの MFC アプリケーションは、Windows のコントロール バーではなく、これらのコントロール バーを使用します。  
  
 [CControlBar](../mfc/reference/ccontrolbar-class.md)  
 MFC コントロール バーの基本クラスは、このセクションを指定します。  コントロール バーをフレーム ウィンドウの端に配置されるウィンドウです。  コントロール バーをツール バー ボタンなど `HWND`に基づいて、`HWND`のベースの子コントロールまたはコントロールが含まれています。  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 ダイアログ ボックス テンプレートに基づくコントロール バーです。  
  
 [CReBar](../mfc/reference/crebar-class.md)  
 コントロールの形式で追加子ウィンドウを含めることができるツール バーをサポートします。  
  
 [CToolBar](../mfc/reference/ctoolbar-class.md)  
 `HWND`に基づいてビットマップ コマンド ボタンを含むツール バー コントロール ウィンドウ。  ほとんどの MFC アプリケーションは `CToolBarCtrl`ではなく、このクラスを使用します。  
  
 [CStatusBar](../mfc/reference/cstatusbar-class.md)  
 ステータス バー コントロールのウィンドウの基本クラス。  ほとんどの MFC アプリケーションは `CStatusBarCtrl`ではなく、このクラスを使用します。  
  
## Windows のコントロール バー  
 これらのコントロール バーに対応する Windows のコントロールの Thin ラッパーです。  これらはフレームワークに統合されていないため、使用する前にリストされているコントロール バーよりも困難です。  ほとんどの MFC アプリケーションは前述のコントロール バーを使用します。  
  
 [CRebarCtrl](../mfc/reference/crebarctrl-class.md)  
 `CRebar` オブジェクトの内部コントロールを実装します。  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 通常、アプリケーションのステータス情報を表示できるペインに水平方向の分割ウィンドウ。  
  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Windows ツール バー コモン コントロールの機能が用意されています。  
  
## 関連クラス  
 [CToolTipCtrl](../Topic/CToolTipCtrl%20Class.md)  
 アプリケーションでツールの目的を説明する、単一行のテキストを表示する小さなポップアップ ウィンドウ。  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 コントロール バーのドッキング状態データの永続ストレージを処理します。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)