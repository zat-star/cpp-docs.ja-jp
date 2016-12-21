---
title: "Selecting Controls | Microsoft Docs"
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
  - "Dialog editor, selecting controls"
  - "dominant controls"
  - "dialog box controls, selecting in editor"
  - "controls [C++], selecting"
  - "size, controls"
  - "controls [C++], dominant"
ms.assetid: 27f05450-4550-4229-9f4c-2c9e06365596
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Selecting Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コントロールを選択し、サイズ変更、配置、移動、コピー、または削除してから、必要な操作を実行します。  ほとんどの場合は、複数のコントロールを選択し、[&#91;ダイアログ エディター&#93; ツール バー](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md)のサイズ変更ツールと配置ツールを使用する必要があります。  
  
 選択したコントロールは、淡色の境界線で囲まれ、その線の上には "サイズ変更ハンドル" が表示されます。サイズ変更ハンドルは小さい四角形であり、塗りつぶし \(アクティブの場合\) または枠線のみ \(アクティブでない場合\) で表示されます。  複数のコントロールを選択した場合、最も優先度の高いコントロールには実線のサイズ変更ハンドルが付き、残りのコントロールには中空のサイズ変更ハンドルが付きます。  
  
 複数のコントロールをサイズ変更または配置する場合、ダイアログ エディターでは "最も優先度の高いコントロール" を使用して、残りのコントロールのサイズや配置の方法が決定されます。  既定では、最も優先度の高いコントロールは最初に選択したコントロールです。  
  
-   [複数のコントロールの選択](../mfc/selecting-multiple-controls.md)  
  
-   [最も優先度の高いコントロールの指定](../mfc/specifying-the-dominant-control.md)  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
## 要件  
 Win32  
  
## 参照  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)