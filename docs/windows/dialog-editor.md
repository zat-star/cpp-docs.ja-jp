---
title: "Dialog Editor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.dialog.dialog"
  - "vc.editors.dialog.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource editors, Dialog editor"
  - "editors, dialog boxes"
  - "Dialog editor"
  - "dialog boxes, editing"
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Dialog Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ エディターを使用すると、ダイアログ ボックス リソースの作成や編集ができます。 \[リソース ビュー\] ウィンドウ \(**\[表示 &#124; リソース ビュー\]**\) のダイアログの .rc ファイルをダブルクリックして、ダイアログ エディターを開きます。 リソース ビューは Express Edition では使用できないことに注意してください。  
  
 ダイアログ ボックスまたはダイアログ ボックス テンプレートを新規作成する場合の最初のステップの 1 つは、ダイアログ ボックスにコントロールを追加することです。 ダイアログ エディターでは、コントロールを特定のサイズ、形状、またはアラインメントに収まるように調整したり、ダイアログ ボックス内での操作のために移動したりできます。 また、コントロールは簡単に削除できます。  
  
 ダイアログ ボックスをテンプレートとして格納すると、後で再利用できます。 また、ダイアログ ボックスのデザインと実装コードの編集の間の切り替えも簡単です。  
  
 さらに、ダイアログ エディターでは、単一または複数のコントロールのプロパティを編集できます。 タブ オーダー、つまり Tab キーが押されたときにコントロールがフォーカスを取得する順序を変更したり、ユーザーがキーボードを使用してコントロールを選択できるように、アクセス キー \(キーの組み合わせ\) を定義したりできます。 事前に設定されているアクセス キーの一覧については、「[ダイアログ エディターのアクセラレータ キー](../mfc/accelerator-keys-for-the-dialog-editor.md)」を参照してください。  
  
 ダイアログ エディターでは、ActiveX コントロールなどのカスタム コントロールを使用することもできます。 さらに、[フォーム ビュー](../mfc/reference/cformview-class.md)、[レコード ビュー](../data/record-views-mfc-data-access.md)、または[ダイアログ バー](../mfc/dialog-bars.md)も編集できます。  
  
 [!INCLUDE[vs_dev14](../mfc/includes/vs_dev14_md.md)] 以降は、ダイアログ エディターを使用して動的なレイアウトを定義し、ユーザーがダイアログのサイズを変更した場合にコントロールがどのように動いてサイズ変更を行うかを指定することができます。 詳細については、「[動的レイアウト](../mfc/dynamic-layout.md)」を参照してください。  
  
-   [ダイアログ ボックスの新規作成](../mfc/creating-a-new-dialog-box.md)  
  
-   [ユーザーが実行時に終了できないダイアログ ボックスの作成](../mfc/creating-a-dialog-box-that-users-cannot-exit.md)  
  
-   [&#91;ダイアログ エディター&#93; ツール バーの表示と非表示](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md)  
  
-   [ダイアログ エディターとコードの切り替え](../Topic/Switching%20Between%20Dialog%20Box%20Controls%20and%20Code.md)  
  
-   [ダイアログ ボックスのコントロール](../mfc/controls-in-dialog-boxes.md)  
  
-   [ダイアログ ボックス コントロールへのイベント ハンドラーの追加](../mfc/adding-event-handlers-for-dialog-box-controls.md)  
  
-   [ダイアログ ボックスのテスト](../mfc/testing-a-dialog-box.md)  
  
-   [ダイアログ エディターのアクセラレータ キー](../mfc/accelerator-keys-for-the-dialog-editor.md)  
  
-   [ダイアログ エディターのトラブルシューティング](../mfc/troubleshooting-the-dialog-editor.md)  
  
    > [!TIP]
    >  ダイアログ エディターをさまざまな状況で使用している場合は、マウスの右ボタンをクリックすると、頻繁に使用するコマンドのショートカット メニューを表示できます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
## 要件  
 Win32  
  
## 参照  
 [Resource Editors](../mfc/resource-editors.md)   
 [コントロール](../mfc/controls-mfc.md)   
 [コントロール クラス](../mfc/control-classes.md)   
 [ダイアログ ボックス クラス](../mfc/dialog-box-classes.md)   
 [ダイアログ ボックス コントロールおよび変数の型](../Topic/Dialog%20Box%20Controls%20and%20Variable%20Types.md)