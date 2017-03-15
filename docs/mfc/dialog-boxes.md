---
title: "ダイアログ ボックス | Microsoft Docs"
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
  - "CDialog クラス, MFC ダイアログ ボックス"
  - "MFC ダイアログ ボックス"
  - "MFC, ダイアログ ボックス"
  - "モーダル ダイアログ ボックス, MFC ダイアログ ボックス"
  - "モードレス ダイアログ ボックス, MFC ダイアログ ボックス"
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ダイアログ ボックス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows 向けのアプリケーションでは、ダイアログ ボックスを通じてユーザーとの対話が頻繁に行われます。  [CDialog](../mfc/reference/cdialog-class.md) クラスには、ダイアログ ボックスを管理するためのインターフェイスがあります。Visual C\+\+ ダイアログ エディターでは、ダイアログ ボックスのデザインや、ダイアログ テンプレート リソースの作成が簡単にできます。コード ウィザードでは、ダイアログ ボックスのコントロールの初期化と妥当性チェックのプロセス、およびユーザーが入力した値の収集プロセスを簡略化します。  
  
 ダイアログ ボックスには、以下のコントロールが含まれます。  
  
-   Windows コモン コントロール \(エディット ボックス、プッシュ ボタン、リスト ボックス、コンボ ボックス、ツリー コントロール、リスト コントロール、プログレス インジケーターなど\)  
  
-   ActiveX コントロール  
  
-   オーナー描画コントロール \(ダイアログ ボックス内での描画に必要なコントロール\)  
  
 ほとんどのダイアログ ボックスはモーダルです。モーダル ダイアログ ボックスの場合は、プログラムのほかの部分を使用する前にダイアログ ボックスを閉じる必要があります。  ダイアログ ボックスは、モードレスとしても作成できます。モードレス ダイアログ ボックスの場合は、ダイアログ ボックスを開いたままでほかのウィンドウを使用できます。  MFC では、`CDialog` クラスによって両方のダイアログ ボックスがサポートされています。  コントロールは、[ダイアログ エディター](../mfc/dialog-editor.md)で作成されるダイアログ テンプレート リソースを使用して配置および管理します。  
  
 タブ ダイアログ ボックスとも呼ばれる[プロパティ シート](../mfc/property-sheets-mfc.md)は、ダイアログ ボックス コントロールを備えた複数の "ページ" を持つダイアログ ボックスです。  各ページには、上部にファイル フォルダーの "タブ" があります。  タブをクリックすると、そのページがダイアログ ボックスの最前面に表示されます。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [例 : メニュー コマンドによるダイアログ ボックスの表示](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)  
  
-   [フレームワークのダイアログ ボックス コンポーネント](../mfc/dialog-box-components-in-the-framework.md)  
  
-   [モーダルとモードレスのダイアログ ボックス](../mfc/modal-and-modeless-dialog-boxes.md)  
  
-   [プロパティ シートとプロパティ ページ](../mfc/property-sheets-and-property-pages-mfc.md) \(ダイアログ ボックス内\)  
  
-   [ダイアログ リソースの作成](../Topic/Creating%20the%20Dialog%20Resource.md)  
  
-   [コード ウィザードによるダイアログ クラスの作成](../mfc/creating-a-dialog-class-with-code-wizards.md)  
  
-   [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)  
  
-   [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](../Topic/Type-Safe%20Access%20to%20Controls%20in%20a%20Dialog%20Box.md)  
  
-   [ダイアログ クラスと Windows メッセージの対応](../mfc/mapping-windows-messages-to-your-class.md)  
  
-   [通常オーバーライドされるメンバー関数](../mfc/commonly-overridden-member-functions.md)  
  
-   [通常追加されるメンバー関数](../Topic/Commonly%20Added%20Member%20Functions.md)  
  
-   [コモン ダイアログ クラス](../mfc/common-dialog-classes.md)  
  
-   [OLE のダイアログ ボックス](../mfc/dialog-boxes-in-ole.md)  
  
-   ユーザー インターフェイスがダイアログ ボックスのアプリケーションを作成する: [CMNCTRL1](../top/visual-cpp-samples.md) または [CMNCTRL2](../top/visual-cpp-samples.md) のサンプル プログラムを参照してください。  このオプションは、アプリケーション ウィザードでも用意されています。  
  
-   [サンプル](../mfc/dialog-sample-list.md)  
  
## 参照  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)