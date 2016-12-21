---
title: "Adding Controls to a Dialog Causes the Dialog to No Longer Function | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "controls [C++], troubleshooting"
  - "common controls, troubleshooting"
  - "troubleshooting controls"
  - "dialog boxes, troubleshooting"
  - "dialog box controls, troubleshooting"
  - "InitCommonControls"
ms.assetid: b2dd4574-ea59-4343-8d65-b387cead5da6
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Controls to a Dialog Causes the Dialog to No Longer Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ ボックスにコモン コントロールやリッチ エディット コントロールを追加しても、ダイアログ ボックスのテスト時に表示されないか、またはダイアログ ボックス自体が表示されません。  
  
 **この問題の例**  
  
1.  Win32 プロジェクトを作成し、コンソール アプリケーションではなく Windows アプリケーションを作成できるように、アプリケーション設定を変更します。  
  
2.  [リソース ビュー](../windows/resource-view-window.md)で、.rc ファイルをダブルクリックします。  
  
3.  ダイアログ オプションの \[バージョン情報\] ボックスをクリックします。  
  
4.  ダイアログ ボックスに IP アドレス コントロールを追加します。  
  
5.  保存して \[すべてリビルド\] をクリックします。  
  
6.  プログラムを実行します。  
  
7.  ダイアログ ボックスで、\[ヘルプ\] メニューの \[バージョン情報\] をクリックしても、ダイアログ ボックスは表示されません。  
  
 **原因**  
  
 現在のダイアログ エディターでは、以下の表に示すコモン コントロールやリッチ エディット コントロールをダイアログ ボックスにドラッグ アンド ドロップしても、プロジェクトにコードが自動的に追加されません。  また、Visual Studio では、この問題が発生してもエラー メッセージや警告メッセージは表示されません。  したがって、コントロールのコードを手動で追加する必要があります。  
  
||||  
|-|-|-|  
|Slider Control|Tree Control|Date Time Picker|  
|Spin Control|Tab Control|Month Calendar|  
|Progress Control|Animation Control|IP Address Control|  
|Hot Key|Rich Edit Control|Combo Box|  
|List Control|Rich Edit 2.0 Control|カスタム コントロール|  
  
## コモン コントロールの場合の解決法  
 ダイアログ ボックスでコモン コントロールを使用するには、ダイアログ ボックスを作成する前に [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) または **AFXInitCommonControls** を呼び出す必要があります。  
  
## リッチ エディット コントロールの場合の解決法  
 リッチ エディット コントロールの場合は、**LoadLibrary** を呼び出す必要があります。  詳細については、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の「[MFC でのリッチ エディット 1.0 コントロールの使用](../Topic/Using%20the%20RichEdit%201.0%20Control%20with%20MFC.md)」と「[About Rich Edit Controls](http://msdn.microsoft.com/library/windows/desktop/bb787873)」、および「[リッチ エディット コントロールの概要](../mfc/overview-of-the-rich-edit-control.md)」を参照してください。  
  
## 要件  
 Win32  
  
## 参照  
 [Troubleshooting the Dialog Editor](../mfc/troubleshooting-the-dialog-editor.md)   
 [Dialog Editor](../mfc/dialog-editor.md)