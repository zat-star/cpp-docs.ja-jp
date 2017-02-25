---
title: "エクスプローラー形式の MFC アプリケーションの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcexplorer.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ブラウザー, エクスプローラー スタイル アプリケーション"
  - "エクスプローラー スタイル アプリケーション, 作成"
  - "MFC アプリケーション, Windows エクスプローラー形式"
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# エクスプローラー形式の MFC アプリケーションの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

多くの Windows システム アプリケーションはファイル エクスプローラーのユーザー インターフェイス \(UI\) \(UI\) を使用します。  たとえば、エクスプローラーを起動すると、クライアント領域を区切る垂直方向の分割バーでアプリケーションを参照します。  クライアント領域の左側には移動と参照の機能があり、右側には左ペインで選択した項目の詳細が表示されます。  ユーザーが左ペインで項目をクリックすると、右ペインの表示内容が更新されます。  MDI アプリケーションでは、**\[表示\]** メニューのコマンドを使用して、右ペインに表示される詳細の表示内容を変更できます。SDI またはマルチ トップレベル ドキュメント アプリケーションでは、詳細の変更に使用できるのはツール バー ボタンだけです。  
  
 ペインの内容はアプリケーションによって異なります。  ファイル システム ブラウザーでは、左ペインにディレクトリ、コンピューター、またはコンピューター グループの階層構造が表示され、右ペインにフォルダー、各ファイル、またはコンピューター、さらにその詳細が表示されます。  ペインの内容はファイルとは限りません。  電子メール メッセージ、エラー レポート、またはデータベース内のその他のアイテムも表示できます。  
  
 ウィザードでは以下のクラスが作成されます。  
  
-   クライアント領域の左ペインを定義する **CLeftView** クラス。  このクラスは必ず [CTreeView](../../mfc/reference/ctreeview-class.md) から派生します。  
  
-   クライアント領域の右ペインを定義する C*ProjName*View クラス。  既定では、このクラスは [CListView](../../mfc/reference/clistview-class.md) から派生しますが、ウィザードの [&#91;生成されたクラス&#93;](../../mfc/reference/generated-classes-mfc-application-wizard.md) ページの \[基本クラス\] ボックスでクラスを指定して、別の種類のビューにすることもできます。  
  
 生成するアプリケーションには、シングル ドキュメント インターフェイス \(SDI: Single Document Interface\)、マルチ ドキュメント インターフェイス \(MDI: Multiple Document Interface\)、またはマルチ トップレベル ドキュメント アーキテクチャを含めることができます。  アプリケーションで作成される各フレーム ウィンドウは、[CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) で左右に分割されます。  このアプリケーション タイプのコーディングは、分割線を使用する通常の MFC アプリケーションのコーディングに似ていますが、各分割ペイン内にそれぞれコントロール ビューがある点が異なります。  
  
 右ペインで既定のリスト ビューを使用する場合は、大きいアイコン、小さいアイコン、一覧、または詳細モードにビューの表示形式を切り替えるための、メニューの選択肢 \(MDI アプリケーションのみ\) およびツール バー ボタンがウィザードによって作成されます。  
  
### 実行可能ファイル エクスプローラー スタイルのな MFC アプリケーションの作成を開始するには  
  
1.  「[MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)」の手順に従って操作します。  
  
2.  MFC アプリケーション ウィザードの [アプリケーションの種類](../Topic/Application%20Type,%20MFC%20Application%20Wizard.md) ページで、**\[エクスプローラー\]** のプロジェクトのスタイルを選択します。  
  
3.  ウィザードのその他のページで、必要なオプションを設定します。  
  
4.  \[完了\] をクリックして、スケルトン アプリケーションを作成します。  
  
 詳細については、次のトピックを参照してください。  
  
-   [複数のドキュメント タイプ、ビュー、フレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [MFC で使用できる派生ビュー クラス](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [アプリケーションのデザイン上の検討事項](../../mfc/application-design-choices.md)  
  
## 参照  
 [MFC アプリケーション ウィザード](../Topic/MFC%20Application%20Wizard.md)   
 [Web ブラウザー形式の MFC アプリケーションの作成](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)   
 [フォーム ベースの MFC アプリケーションの作成](../Topic/Creating%20a%20Forms-Based%20MFC%20Application.md)