---
title: "Associating Menu Commands with Status Bar Text in MFC Applications | Microsoft Docs"
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
  - "status bars, associating menu items"
  - "menus, status bar text"
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Associating Menu Commands with Status Bar Text in MFC Applications
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーションでは、ユーザーが選択する各メニュー コマンドに対して、説明のテキストを表示できます。 そのためには、\[プロパティ\] ウィンドウの **\[プロンプト\]** プロパティを使用し、各メニュー コマンドにテキスト文字列を割り当てます。 コマンドと同じ ID を持つ[ストリング テーブル](../mfc/string-editor.md)に文字列がある場合、MFC アプリケーションでは、ユーザーがマウス ポインターをメニュー項目の上に置くと、実行中のアプリケーションのステータス バーにこの文字列リソースが自動的に表示されます。  
  
### メニュー コマンドをステータス バーのテキスト文字列に関連付けるには  
  
1.  **メニュー** エディターで、メニュー コマンドを選択します。  
  
2.  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)で、関連付けるステータス バーのテキストを **\[プロンプト\]** ボックスに入力します。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
 **必要条件**  
  
 MFC  
  
## 参照  
 [文字列](../atl-mfc-shared/strings-atl-mfc.md)   
 [Adding Commands to a Menu](../Topic/Adding%20Commands%20to%20a%20Menu.md)   
 [Menu Editor](../Topic/Menu%20Editor.md)