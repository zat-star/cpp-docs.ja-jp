---
title: "MDI タブ付きグループ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- mdi [MFC], tabbed groups
- tabbed grous [MFC]
ms.assetid: 0a464f36-39b7-4e68-8b67-ec175de28377
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9606d28f6e2057072a0c9fc356e3bc7ca7cdc19b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mdi-tabbed-groups"></a>MDI タブ付きグループ
マルチ ドキュメント インターフェイス (MDI) タブ付きグループの機能により、複数のドキュメント インターフェイス (MDI) アプリケーションに 1 つまたは複数のタブ付きウィンドウを表示する (またはタブ付きウィンドウと呼ばれるグループ*タブ付きグループ*) MDI クライアント領域にします。 垂直または水平方向には、タブ付きウィンドウを整列することができます。 アプリケーションでは、1 つ以上の MDI タブ付きグループをホストしている場合、グループは分割線で区切られます。  
  
## <a name="features"></a>フィーチャー  
 MDI タブ付きグループの機能を次に示します。  
  
-   アプリケーションは、タブ付きウィンドウを動的に作成できます。  
  
-   アプリケーションは、水平方向または垂直方向、タブ付きウィンドウを整列できます。  
  
-   タブ付きウィンドウのグループは、分割線で区切られます。 ユーザーは、スプリッターを使用して、タブ付きグループのサイズを変更できます。  
  
-   ユーザーは、グループ間で個々 のタブをドラッグすることができます。  
  
-   ユーザーは、新しいグループを作成する個々 のタブをドラッグできます。  
  
-   ユーザーでは、タブを移動したり、ショートカット メニューを使用して、新しいグループを作成することができます。  
  
-   アプリケーションは、保存して、タブ付きウィンドウのレイアウトを読み込むことができます。  
  
-   アプリケーションは、保存して、MDI ドキュメントの一覧を読み込むことができます。  
  
-   アプリケーションでは、個々 のタブ付きグループにアクセスでき、そのパラメーターを変更することができます。  
  
### <a name="using-mdi-tabbed-groups"></a>使用して MDI タブ付きグループ  
 MDI タブ付きグループで一般的に実行されるタスクを次に示します。  
  
-   メイン フレーム ウィンドウの MDI タブ付きグループを有効にするを呼び出す[cmdiframewndex::enablemditabbedgroups](../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups)です。 このメソッドの 2 番目のパラメーターがのインスタンス、`CMDITabInfo`クラスです。 呼び出す前に、それらを変更または既定のパラメーターを使用できます`CMDIFrameWndEx::EnableMDITabbedGroups`です。  
  
-   実行時に MDI タブ付きグループのプロパティを変更するには、作成または変更、`CMDITabInfo`オブジェクトと呼び出し`CMDIFrameWndEx::EnableMDITabbedGroups`再度  
  
-   タブ付きウィンドウの MDI の一覧を取得する、呼び出し`CMDIFrameWndEx::GetMDITabGroups`です。  
  
-   アクティブなタブ付きグループの横にある新しい MDI タブ付きグループを作成するには`CMDIFrameWndEx::MDITabNewGroup`します。  
  
-   入力フォーカスを移動してタブ付きグループの前または次のウィンドウに、呼び出す`CMDIFrameWndEx::MDITabMoveToNextGroup`です。  
  
-   タブ付きグループの呼び出しをウィンドウ、MDI のメンバーであるかどうかを判断する`CMDIFrameWndEx::IsMemberOfMDITabGroup`です。  
  
-   MDI タブまたは MDI タブ付きグループがメイン フレーム ウィンドウに対して有効にするかどうかを確認するのには、呼び出す`CMDIFrameWndEx::AreMDITabs`です。 MDI タブ付きグループが有効になっているかどうかをのみか、呼び出す`CMDIFrameWndEx::IsMDITabbedGroup`です。  
  
-   ユーザーがタブをクリックするか、別の MDI タブ付きグループにドラッグ、ショートカット メニューを表示するオーバーライド`CMDIFrameWndEx::OnShowMDITabContextMenu`で、 `CMDIFrameWndEx`-クラスを派生します。 このメソッドを実装しない場合、アプリケーションには、ショートカット メニューは表示されません。  
  
-   MDI タブ付きグループのレイアウトをアプリケーションを保存する`CMDIFrameWndEx::SaveMDIState`です。 タブ付きグループのプロファイルを以前に保存した MDI を読み込み、呼び出す`CMDIFrameWndEx::LoadMDIState`です。 読み込みまたは MDI アプリケーションで開いているドキュメントのリストを保存するこれらのメソッドを呼び出すこともできます。 保存と読み込み MDI 状態の詳細については、次を参照してください。 [CMDIFrameWndEx::LoadMDIState](../mfc/reference/cmdiframewndex-class.md#loadmdistate)です。  
  
## <a name="see-also"></a>参照  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)   
 [CMDIFrameWndEx クラス](../mfc/reference/cmdiframewndex-class.md)   
 [CMDIChildWndEx クラス](../mfc/reference/cmdichildwndex-class.md)   
 [CMDITabInfo クラス](../mfc/reference/cmditabinfo-class.md)
