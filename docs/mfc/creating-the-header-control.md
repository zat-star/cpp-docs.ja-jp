---
title: "ヘッダー コントロールの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CHeaderCtrl クラス, 作成"
  - "ヘッダー コントロール, 作成"
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ヘッダー コントロールの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ヘッダー コントロールは、ヘッダー コントロールを含むリスト コントロールを追加するには、ダイアログ エディターでは使用できません。  
  
### ヘッダー コントロールをダイアログ ボックスに配置するには  
  
1.  手動でダイアログ クラスの型 [CHeaderCtrl](../Topic/CHeaderCtrl%20Class.md) のメンバー変数を埋め込みます。  
  
2.  [OnInitDialog](../Topic/CDialog::OnInitDialog.md)で作成、`CHeaderCtrl`のスタイルを設定し、それを配置して、表示します。  
  
3.  ヘッダー コントロールに項目を追加します。  
  
4.  これを処理する必要があるヘッダー コントロール通知メッセージのダイアログ クラスのハンドラー関数をマップするには、プロパティ ウィンドウを使用します。[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)を参照してください。  
  
### ビューではなく CListView\) にヘッダー コントロールを配置するには  
  
1.  クラス ビューで [CHeaderCtrl](../Topic/CHeaderCtrl%20Class.md) オブジェクトを埋め込みます。  
  
2.  スタイル、位置は、ビューの [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) のメンバー関数のヘッダー コントロール ウィンドウを表示します。  
  
3.  ヘッダー コントロールに項目を追加します。  
  
4.  これを処理する必要があるヘッダー コントロール通知メッセージのビュー クラスのハンドラー関数をマップするには、プロパティ ウィンドウを使用します。[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)を参照してください。  
  
 いずれの場合も、埋め込みコントロール オブジェクトはビューまたはダイアログ オブジェクトが作成されたときに作成されます。  その後、コントロール ウィンドウを作成するに [CHeaderCtrl::Create](../Topic/CHeaderCtrl::Create.md) を呼び出す必要があります。  コントロール、呼び出し [CHeaderCtrl::Layout](../Topic/CHeaderCtrl::Layout.md) をコントロールの目的の位置を設定する初期サイズを確認し、配置するように設定すると [SetWindowPos](../Topic/CWnd::SetWindowPos.md) を。  次 [ヘッダー コントロールに項目を追加します。](../mfc/adding-items-to-the-header-control.md)"に説明されているように項目を追加します。  
  
 詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [ヘッダー コントロールの作成](http://msdn.microsoft.com/library/windows/desktop/bb775238) を参照します。  
  
## 参照  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)