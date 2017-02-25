---
title: "Custom Controls in the Dialog Editor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Custom Control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [C++], templates"
  - "custom controls [Visual Studio], dialog boxes"
  - "custom controls [Visual Studio]"
  - "dialog box controls, custom (user) controls"
  - "Dialog editor, custom controls"
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Custom Controls in the Dialog Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ エディターを使用すると、既存の "カスタム" コントロールや "ユーザー" コントロールをダイアログ ボックス テンプレートで使用できます。  
  
> [!NOTE]
>  この場合のカスタム コントロールを ActiveX コントロールと混同しないでください。  ActiveX コントロールは以前に OLE カスタム コントロールと呼ばれていました。  また、この場合のコントロールを Windows でのオーナー描画コントロールと混同しないでください。  
  
 この機能は、Windows で用意されていないコントロールを使用できるようにするためのものです。  実行時には、コントロールはウィンドウ クラス \(C\+\+ クラスとは異なります\) に関連付けられます。  このタスクを実現する一般的な方法は、ダイアログ ボックスに静的コントロールなどのコントロールをインストールすることです。  実行時には、そのコントロールを [OnInitDialog](../Topic/CDialog::OnInitDialog.md) 関数内で削除し、カスタム コントロールに置き換えます。  
  
 これは、旧式のテクニックです。  ほとんどの場合は、ActiveX コントロールを記述するか、または Windows コモン コントロールをサブクラス化することをお勧めします。  
  
 この種のカスタム コントロールには、以下の制限があります。  
  
-   ダイアログ ボックス内での位置の設定。  
  
-   キャプションの入力。  
  
-   コントロールのウィンドウ クラス名の識別。アプリケーション コードでは、この名前でコントロールを登録する必要があります。  
  
-   コントロールのスタイルを設定する 32 ビットの 16 進値の入力。  
  
-   拡張スタイルの設定。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
## 要件  
 Win32  
  
## 参照  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)