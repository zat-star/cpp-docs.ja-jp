---
title: "Toolbar Button Properties | Microsoft Docs"
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
  - "size, toolbar buttons"
  - "toolbar buttons (in Toolbar editor), setting properties"
  - "Toolbar editor, toolbar button properties"
  - "status bars, active toolbar button text"
  - "command IDs, toolbar buttons"
  - "width, toolbar buttons"
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Toolbar Button Properties
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ツール バー ボタンのプロパティは、次のとおりです。  
  
|プロパティ|Description|  
|-----------|-----------------|  
|**ID**|ボタンの ID を定義します。  ドロップダウン リストに共通の ID 名が表示されます。|  
|**幅**|ボタンの幅を設定します。  推奨値は 16 ピクセルです。|  
|**高さ**|ボタンの高さを設定します。  1 つのボタンの高さがツール バーのすべてのボタンの高さに反映されるので注意してください。  推奨値は 15 ピクセルです。|  
|**\[確認\]**|ステータス バーに表示されるメッセージを定義します。  \\n および名前を追加すると、ツール バー ボタンにツール ヒントが追加されます。  詳細については、「[ツール バー ボタンのツール ヒントの作成](../mfc/creating-a-tool-tip-for-a-toolbar-button.md)」を参照してください。|  
  
 **\[Width\]** と **\[Height\]** はすべてのボタンに適用されます。  ツール バーの作成に使用するビットマップの最大幅は 2048 です。  したがって、ボタンの幅を 512 に設定するとボタンを 4 つしか追加できず、幅を 513 に設定するとボタンを 3 つしか追加できません。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
## 要件  
 MFC または ATL  
  
## 参照  
 [Changing the Properties of a Toolbar Button](../mfc/changing-the-properties-of-a-toolbar-button.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)