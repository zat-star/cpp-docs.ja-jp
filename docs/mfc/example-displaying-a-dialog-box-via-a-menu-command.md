---
title: "例 : メニュー コマンドによるダイアログ ボックスの表示 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ダイアログ ボックス, MFC"
  - "例 [MFC], ダイアログ ボックス"
  - "メニュー項目, 例"
  - "MFC ダイアログ ボックス, 表示"
  - "MFC ダイアログ ボックス, 例"
  - "モーダル ダイアログ ボックス, 表示"
  - "モードレス ダイアログ ボックス, 表示"
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 例 : メニュー コマンドによるダイアログ ボックスの表示
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、プロシージャが含まれています:  
  
-   メニュー コマンドからモーダル ダイアログ ボックスを表示します。  
  
-   メニュー コマンドからモードレス ダイアログ ボックスを表示します。  
  
 サンプル プロシージャは両方の MFC アプリケーションでは、[MFC アプリケーション ウィザード](../Topic/MFC%20Application%20Wizard.md)で作成したアプリケーションで機能します。  
  
 手順は次の名前と値を使用して T:  
  
|項目|名前か値|  
|--------|----------|  
|アプリケーション|DisplayDialog|  
|メニュー コマンド|表示メニューのコマンド;をテストします。ID \= ID\_VIEW\_TEST です。|  
|ダイアログ ボックス|ダイアログ ボックスのテスト。; クラス CTestDialog \=; ヘッダー ファイル TestDialog.h \=; 変数 testdlg \=、ptestdlg|  
|コマンド ハンドラー|OnViewTest|  
  
### モーダル ダイアログ ボックスを表示します。  
  
1.  メニュー コマンドを作成します。; [メニューまたはメニュー項目の作成](../windows/creating-a-menu.md)を参照してください。  
  
2.  ダイアログ ボックスを作成します。; [ダイアログ エディターを開く](../mfc/creating-a-new-dialog-box.md)を参照してください。  
  
3.  ダイアログ ボックスのクラスを追加します。  詳細については、" [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md) を参照してください。  
  
4.  **\[クラス ビュー\]** のドキュメント クラス \(CDisplayDialogDoc\) を選択します。  **\[プロパティ\]** ウィンドウで、**イベント** ボタンをクリックします。  **\[プロパティ\]** ウィンドウの左ペインのメニュー コマンド \(ID\_VIEW\_TEST\) の ID をダブルクリックし、**コマンド**を選択します。  右ペインで、下向きの矢印をクリックし、**\<Add\> OnViewTest**を選択します。  
  
     MDI アプリケーションのメインフレームにメニュー コマンドを追加すると、アプリケーション クラス \(CDisplayDialogApp\) を選択します。  
  
5.  次を含む既存の後に CDisplayDialogDoc.cpp \(または CDisplayDialogApp.cpp\) にステートメントを含むステートメントを追加する:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
6.  関数を実装するに `OnViewTest` に次のコードを追加する:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#43](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_2.cpp)]  
  
### モードレス ダイアログ ボックスを表示します。  
  
1.  選択を除くモーダル ダイアログ ボックスを表示するには、最初の手順 4 を手順 4.のビュー クラス \(CDisplayDialogView\) します。  
  
2.  DisplayDialogView.h を編集する:  
  
    -   最初のクラス宣言の前にダイアログ ボックス クラスを宣言する:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#44](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_3.h)]  
  
    -   属性のパブリック セクションの後にダイアログ ボックスへのポインターを宣言する:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#45](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_4.h)]  
  
3.  DisplayDialogView.cpp を編集する:  
  
    -   次を含む既存の後にステートメントを含むステートメントを追加する:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
    -   コンストラクターに次のコードを追加する:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#46](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_5.cpp)]  
  
    -   デストラクターに次のコードを追加する:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#47](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_6.cpp)]  
  
    -   関数を実装するに `OnViewTest` に次のコードを追加する:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#48](../mfc/codesnippet/CPP/example-displaying-a-dialog-box-via-a-menu-command_7.cpp)]  
  
 また、次のサポート技術情報の文書を参照してください。:  
  
-   Q251059: " HOWTO: MFC Dialog Box に独自のウィンドウ クラスの名前を指定します。  
  
## 参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [モーダルとモードレスのダイアログ ボックス](../mfc/modal-and-modeless-dialog-boxes.md)