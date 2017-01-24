---
title: "How to: Search for Symbols in Resources | Microsoft Docs"
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
  - "symbols, finding"
  - "resources [Visual Studio], searching for symbols"
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Search for Symbols in Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### リソース内のシンボルを検索するには  
  
1.  **\[編集\]** メニューの **\[シンボルの検索\]** を選択します。  
  
2.  [&#91;シンボルの検索&#93;](http://msdn.microsoft.com/ja-jp/63e93d9c-784f-418d-a76a-723da5ff5d96) ダイアログ ボックスの **\[検索する文字列\]** ボックスの一覧から以前の検索文字列を選択するか、または「ID\_ACCEL1」のように、検索するアクセラレータ キーを入力します。  
  
    > [!TIP]
    >  検索に[正規表現](../Topic/Using%20Regular%20Expressions%20in%20Visual%20Studio.md)を使用するには、**\[編集\]** メニューの **\[シンボルの検索\]** コマンドではなく [&#91;フォルダーを指定して検索&#93;](../Topic/Find%20Command.md) コマンドを使用する必要があります。  正規表現を有効にするには、[&#91;検索&#93;](http://msdn.microsoft.com/ja-jp/dad03582-4931-4893-83ba-84b37f5b1600) ダイアログ ボックスの **\[使用: 正規表現\]** チェック ボックスをオンにしてください。  次に、**\[検索する文字列\]** ボックスの右側にある右矢印ボタンをクリックすると、検索の正規表現のリストを表示できます。  このリストで正規表現を選択すると、**\[検索する文字列\]** ボックスの検索文字列として設定されます。  
  
3.  **\[検索\]** オプションのいずれかを選択します。  
  
4.  **\[次を検索\]** をクリックします。  
  
    > [!NOTE]
    >  文字列リソース、アクセラレータ リソース、またはバイナリ リソース内のシンボルは検索できません。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 **必要条件**  
  
 Win32  
  
## 参照  
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)