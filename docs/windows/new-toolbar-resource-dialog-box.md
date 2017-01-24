---
title: "[新規ツール バー] ダイアログ ボックス | Microsoft Docs"
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
  - "vc.editors.newtoolbarresource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "[新規ツール バー リソース] ダイアログ ボックス"
ms.assetid: 52dd01ad-e748-4ab2-b3eb-59f5df990ca6
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# [新規ツール バー] ダイアログ ボックス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\[新規ツール バー\] ダイアログ ボックスでは、ツール バー リソースに追加するボタンの幅と高さを指定できます。  既定では 16 × 15 ピクセルです。  
  
 ツール バーの作成に使用するビットマップの最大幅は 2048 です。  したがって、\[Width\] を 512 に設定すると、ボタンを 4 つしか追加できません。  幅を 513 に設定すると、ボタンを 3 つしか追加できません。  
  
 **\[Width\]**  
 ビットマップ リソースからツール バー リソースに変換するツール バー ボタンの幅を入力します。  イメージは指定した幅と高さにトリミングされ、色は標準ツール バーの色 \(16 色\) を使用するように調整されます。  
  
 **\[Height\]**  
 ビットマップ リソースからツール バー リソースに変換するツール バー ボタンの高さを入力します。  イメージは指定した幅と高さにトリミングされ、色は標準ツール バーの色 \(16 色\) を使用するように調整されます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
## 要件  
 MFC または ATL  
  
## 参照  
 [Toolbar Button Properties](../mfc/toolbar-button-properties.md)   
 [Converting Bitmaps to Toolbars](../mfc/converting-bitmaps-to-toolbars.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)