---
title: "Viewing and Adding ActiveX Controls to a Dialog Box | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.controls.activex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dialog boxes [C++], adding ActiveX controls"
  - "Insert ActiveX Control command"
  - "ActiveX controls [C++], adding to dialog boxes"
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Viewing and Adding ActiveX Controls to a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio では、ActiveX コントロールをダイアログ ボックスに挿入することができます。  
  
### 使用可能な ActiveX コントロールを表示するには  
  
1.  ダイアログ エディターでダイアログ ボックスを開きます。  
  
2.  ダイアログ ボックスの本体の任意の場所を右クリックします。  
  
3.  ショートカット メニューで、**\[ActiveX コントロールの挿入\]** をクリックします。  
  
     [&#91;ActiveX コントロールの挿入&#93; ダイアログ ボックス](../Topic/Insert%20ActiveX%20Control%20Dialog%20Box.md)が表示され、システム上のすべての ActiveX コントロールが表示されます。 ダイアログ ボックスの下部には、ActiveX コントロール ファイルへのパスが表示されます。  
  
### ダイアログ ボックスに ActiveX コントロールを追加するには  
  
1.  [&#91;ActiveX コントロールの挿入&#93; ダイアログ ボックス](../Topic/Insert%20ActiveX%20Control%20Dialog%20Box.md)で、ダイアログ ボックスに追加するコントロールを選択し、**\[OK\]** をクリックします。  
  
     コントロールがダイアログ ボックスに表示されます。このダイアログ ボックスで、他のコントロールでするのと同じように、コントロールの編集またはそのハンドラーの作成を行います。  
  
    > [!NOTE]
    >  ActiveX コントロールを [&#91;ツールボックス&#93; ウィンドウ](../Topic/Toolbox.md)に追加することができます。 詳細については、「[ツールボックスの項目とタブの管理](http://msdn.microsoft.com/ja-jp/21285050-cadd-455a-b1f5-a2289a89c4db)」をご参照ください。  
  
    > [!CAUTION]
    >  システム上の ActiveX コントロールの中には、配布が法的に許可されていないものもあります。 コントロールをインストールしたソフトウェアのライセンス契約を参照するか、ソフトウェア会社に問い合わせてください。  
  
     アクセスしやすいようにツールボックス ウィンドウにコントロールを配置することができます。 詳細については、「[&#91;ツールボックスのカスタマイズ&#93; ダイアログ ボックス](http://msdn.microsoft.com/ja-jp/bd07835f-18a8-433e-bccc-7141f65263bb)」をご参照ください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
 **要件**  
  
 Win32  
  
## 参照  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)