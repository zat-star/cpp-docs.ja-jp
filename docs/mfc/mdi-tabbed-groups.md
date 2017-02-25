---
title: "MDI タブ付きグループ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MDI, タブ付きグループ"
  - "タブ付きグループ"
ms.assetid: 0a464f36-39b7-4e68-8b67-ec175de28377
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# MDI タブ付きグループ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マルチ ドキュメント インターフェイス \(MDI: Multiple Document Interface\) のタブ付きグループ機能を使用すると、マルチ ドキュメント インターフェイス \(MDI\) アプリケーションで、1 つ以上のタブ付きウィンドウ \(または、*タブ付きグループ*と呼ばれるタブ付きウィンドウのグループ\) を MDI クライアント領域に表示できます。  タブ付きウィンドウは、水平または垂直に配置できます。  アプリケーションが複数の MDI タブ付きグループをホストしている場合、グループは分割線によって区切られます。  
  
## 機能  
 MDI タブ付きグループの機能を次に示します。  
  
-   アプリケーションは、タブ付きウィンドウを動的に作成できます。  
  
-   アプリケーションは、タブ付きウィンドウを水平または垂直に配置できます。  
  
-   タブ付きウィンドウのグループは、分割線で区切られます。  ユーザーは、分割線を使用してタブ付きグループのサイズを変更できます。  
  
-   ユーザーは、個々のタブをグループ間でドラッグできます。  
  
-   ユーザーは、個々のタブをドラッグして新しいグループを作成できます。  
  
-   ユーザーは、ショートカット メニューを使用してタブを移動したり新しいグループを作成したりできます。  
  
-   アプリケーションは、タブ付きウィンドウのレイアウトの保存および読み込みを実行できます。  
  
-   アプリケーションは、MDI ドキュメントの一覧の保存および読み込みを実行できます。  
  
-   アプリケーションは、個々のタブ付きグループにアクセスしてそのパラメーターを変更できます。  
  
### MDI タブ付きグループの使用  
 MDI タブ付きグループを使用して実行される一般的なタスクを次に示します。  
  
-   メイン フレーム ウィンドウで MDI タブ付きグループを有効にするには、[CMDIFrameWndEx::EnableMDITabbedGroups](../Topic/CMDIFrameWndEx::EnableMDITabbedGroups.md) を呼び出します。  このメソッドの 2 番目のパラメーターは、`CMDITabInfo` クラスのインスタンスです。  既定のパラメーターを使用することも、`CMDIFrameWndEx::EnableMDITabbedGroups` を呼び出す前にパラメーターを変更することもできます。  
  
-   実行時に MDI タブ付きグループのプロパティを変更するには、`CMDITabInfo` オブジェクトを作成または変更し、`CMDIFrameWndEx::EnableMDITabbedGroups` を再度呼び出します。  
  
-   MDI タブ付きウィンドウの一覧を取得するには、`CMDIFrameWndEx::GetMDITabGroups` を呼び出します。  
  
-   アクティブな MDI タブ付きグループの横に新しいタブ付きグループを作成するには、`CMDIFrameWndEx::MDITabNewGroup` を呼び出します。  
  
-   タブ付きグループの直前または次のウィンドウに入力フォーカスを移動するには、`CMDIFrameWndEx::MDITabMoveToNextGroup` を呼び出します。  
  
-   ウィンドウが MDI タブ付きグループのメンバーであるかどうかを確認するには、`CMDIFrameWndEx::IsMemberOfMDITabGroup` を呼び出します。  
  
-   メイン フレーム ウィンドウで MDI タブまたは MDI タブ付きグループが有効になっているかどうかを確認するには、`CMDIFrameWndEx::AreMDITabs` を呼び出します。  MDI タブ付きグループが有効になっているかどうかだけを確認するには、`CMDIFrameWndEx::IsMDITabbedGroup` を呼び出します。  
  
-   ユーザーがタブをクリックするか、別の MDI タブ付きグループにタブをドラッグしたときにショートカット メニューが表示されるようにするには、`CMDIFrameWndEx` の派生クラスで `CMDIFrameWndEx::OnShowMDITabContextMenu` をオーバーライドします。  このメソッドを実装しない場合、アプリケーションにはショートカット メニューが表示されません。  
  
-   アプリケーションで MDI タブ付きグループのレイアウトを保存するには、`CMDIFrameWndEx::SaveMDIState` を呼び出します。  以前に保存した MDI タブ付きグループのプロファイルを読み込むには、`CMDIFrameWndEx::LoadMDIState` を呼び出します。  これらのメソッドを呼び出して、MDI アプリケーションで開いているドキュメントの一覧の読み込みまたは保存を実行することもできます。  MDI 状態の保存および読み込みの詳細については、「[CMDIFrameWndEx::LoadMDIState](../Topic/CMDIFrameWndEx::LoadMDIState.md)」を参照してください。  
  
## 参照  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)   
 [CMDIFrameWndEx クラス](../Topic/CMDIFrameWndEx%20Class.md)   
 [CMDIChildWndEx クラス](../Topic/CMDIChildWndEx%20Class.md)   
 [CMDITabInfo クラス](../Topic/CMDITabInfo%20Class.md)