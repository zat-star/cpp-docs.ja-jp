---
title: "[ダイアログ エディター] タブ ([ツールボックス]) | Microsoft Docs"
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
  - "ツールボックス [C++]、[ダイアログ エディター] タブ"
  - "コントロール [C++]、種類"
  - "Syslink コントロール (ダイアログ ボックスの)"
  - "カスタム コントロール [Visual Studio]、ダイアログ ボックス"
  - "コントロール [C++]、標準"
  - "ダイアログ エディター、コントロールの作成"
  - "コントロール [C++]、追加 (ダイアログ ボックスに)"
ms.assetid: 253885c2-dcb9-4d8e-ac9b-805ea31cbf5e
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# [ダイアログ エディター] タブ ([ツールボックス])
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ エディターで作業する場合、\[ダイアログ エディター\] タブが [&#91;ツールボックス&#93; ウィンドウ](../Topic/Toolbox.md)表示されます。 新しいダイアログ ボックスにコントロールを追加するには、作成しようとしているダイアログ ボックスまでツールボックスからコントロールをドラッグします \(詳しくは、「[ダイアログ ボックスにコントロールを追加する](../mfc/adding-a-control-to-a-dialog-box.md)」ご覧ください\)。 次いでコントロールの移動、またはサイズと形状の変更ができます。  
  
 ツールボックスで使用できる標準コントロールは次のとおりです。  
  
-   [Button コントロール](../mfc/reference/cbutton-class.md)  
  
-   [チェック ボックス コントロール](../mfc/reference/button-styles.md)  
  
-   [コンボ ボックス コントロール](../mfc/reference/ccombobox-class.md)  
  
-   [編集コントロール](../Topic/CEdit%20Class.md)  
  
-   グループ ボックス  
  
-   [リスト ボックス コントロール](../Topic/CListBox%20Class.md)  
  
-   [ラジオ ボタン コントロール](../mfc/reference/button-styles.md)  
  
-   [スタティック テキスト コントロール](../Topic/CStatic%20Class.md)  
  
-   [画像コントロール](../mfc/reference/cpictureholder-class.md)  
  
-   [リッチ エディット 2.0 コントロール](../mfc/using-cricheditctrl.md)  
  
-   [スクロール バー コントロール](../mfc/reference/cscrollbar-class.md)  
  
 ツールボックスで使用できる [Windows コモン コントロール](../mfc/controls-mfc.md)によって、アプリケーションで高度な機能が使用できます。 Windows コモン コントロールには以下が含まれます。  
  
-   [スライダー コントロール](../Topic/Slider%20Control%20Styles.md)  
  
-   [スピン コントロール](../mfc/using-cspinbuttonctrl.md)  
  
-   [プログレス コントロール](../mfc/styles-for-the-progress-control.md)  
  
-   [ホット キー コントロール](../Topic/Using%20a%20Hot%20Key%20Control.md)  
  
-   [リスト コントロール](../mfc/list-control-and-list-view.md)  
  
-   [ツリー コントロール](../Topic/Tree%20Control%20Styles.md)  
  
-   [タブ コントロール](../Topic/Tab%20Controls%20and%20Property%20Sheets.md)  
  
-   [アニメーション コントロール](../mfc/using-an-animation-control.md)  
  
-   [日時指定コントロール](../mfc/creating-the-date-and-time-picker-control.md)  
  
-   [月間予定表コントロール](../Topic/Month%20Calendar%20Control%20Examples.md)  
  
-   [IP アドレス コントロール](../mfc/reference/cipaddressctrl-class.md)  
  
-   [拡張コンボ ボックス コントロール](../mfc/creating-an-extended-combo-box-control.md)  
  
-   [カスタム コントロール](../mfc/custom-controls-in-the-dialog-editor.md)  
  
 ツールボックスの **\[カスタム コントロール\]** アイコンを選んで、それをダイアログ ボックスにドラッグすることで、カスタム コントロールをダイアログ ボックスに追加できます。 Syslink コントロールを追加するには、カスタム コントロールを追加し、コントロールの **\[クラス\]** プロパティを **\[Syslink\]** に変更します。 これにより、プロパティが更新され、Syslink コントロールのプロパティが表示されます。 MFC ラッパー クラスについては、「[CLinkCtrl](../mfc/reference/clinkctrl-class.md)」をご覧ください。  
  
 [ダイアログ ボックスに ActiveX コントロールを追加する](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md)こともできます。  
  
 また、より簡単に使用できるようにツールボックス ウィンドウをカスタマイズすることもできます。 詳しくは、「[ツールボックスの項目とタブの管理](http://msdn.microsoft.com/ja-jp/21285050-cadd-455a-b1f5-a2289a89c4db)」をご覧ください。 たとえば、アクセスしやすいようにツールボックス ウィンドウにコントロールを配置することができます。 詳しくは、「[ツールボックスのダイアログ ボックスのカスタマイズ](http://msdn.microsoft.com/ja-jp/bd07835f-18a8-433e-bccc-7141f65263bb)」をご覧ください。  
  
 MFC でのリッチ エディット 1.0 コントロールの使用について詳しくは、「[MFC での RichEdit 1.0 コントロールの使用](../Topic/Using%20the%20RichEdit%201.0%20Control%20with%20MFC.md)」をご覧ください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
## 要件  
 Win32  
  
## 参照  
 [コントロール](../mfc/controls-mfc.md)   
 [コントロール クラス](../mfc/control-classes.md)   
 [ダイアログ ボックス クラス](../mfc/dialog-box-classes.md)   
 [スクロール バー スタイル](../mfc/reference/scroll-bar-styles.md)   
 [リッチ エディット コントロールの例](../Topic/Rich%20Edit%20Control%20Examples.md)   
 [Adding Event Handlers for Dialog Box Controls](../mfc/adding-event-handlers-for-dialog-box-controls.md)   
 [ダイアログ ボックス コントロールおよび変数の型](../Topic/Dialog%20Box%20Controls%20and%20Variable%20Types.md)