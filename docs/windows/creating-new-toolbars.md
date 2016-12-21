---
title: "Creating New Toolbars | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.toolbar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "toolbars [C++], creating"
  - "Toolbar editor, creating new toolbars"
  - "Insert Resource"
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating New Toolbars
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### ツール バーを新規作成するには  
  
1.  リソース ビューで .rc ファイルを右クリックし、ショートカット メニューの \[リソースの追加\] をクリックします。  .rc ファイルに既存のツール バーがある場合は、単に \[Toolbar\] フォルダーを右クリックし、ショートカット メニューの \[Toolbar を挿入\] をクリックします。  
  
     **メモ** プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  \[リソースの追加\] ダイアログ ボックスで、\[リソースの種類\] ボックスの一覧の \[Toolbar\] を選択し、\[新規作成\] をクリックします。  
  
     リソースの種類の \[Toolbar\] の横に正符号 \(\+\) が表示されている場合は、ツール バーのテンプレートを使用できます。  正符号をクリックしてテンプレートの一覧を展開します。次に、テンプレートを選択し、\[新規作成\] をクリックします。  
  
     または  
  
3.  [既存のビットマップからツール バーに変換します](../mfc/converting-bitmaps-to-toolbars.md)。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 MFC または ATL  
  
## 参照  
 [Toolbar Editor](../mfc/toolbar-editor.md)