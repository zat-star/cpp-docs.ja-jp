---
title: "Creating Pop-up Menus | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "context menus, Menu Editor"
  - "pop-up menus, creating"
  - "menus, pop-up"
  - "menus, creating"
  - "shortcut menus, creating"
  - "pop-up menus, displaying"
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating Pop-up Menus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[ポップアップ メニュー](../mfc/menus-mfc.md)には、頻繁に使用するコマンドが表示されます。 これらは状況依存となっていて、マウス ポインターの場所に応じて表示できます。 アプリケーションでポップアップ メニューを使用には、メニュー自体をビルドし、アプリケーション コードに接続する必要があります。  
  
 メニュー リソースを作成したら、アプリケーション コードでメニュー リソースを読み込み、[TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) を使用してメニューを表示する必要があります。 ユーザーがメニューの外部をクリックしてポップアップ メニューを閉じるか、コマンドをクリックすると、この関数に戻ります。 ユーザーがコマンドを選択した場合は、そのコマンドのメッセージが、ハンドルが渡されたウィンドウに送信されます。  
  
### ポップアップ メニューを作成するには  
  
1.  空のタイトルで[メニューを作成](../windows/creating-a-menu.md)します \(**キャプション**は指定しません\)。  
  
2.  [新しいメニューにメニュー コマンドを追加](../Topic/Adding%20Commands%20to%20a%20Menu.md)します。 空のメニュー タイトルの下にある最初のメニュー コマンドに移動します \(一時的なキャプションには、\[ここに入力\] と表示されます\)。**キャプション**とその他の情報を入力します。  
  
     ポップアップ メニューのその他のメニュー コマンドに対して、この手順を繰り返します。  
  
3.  メニュー リソースを保存します。  
  
    > [!TIP]
    >  ポップアップ メニューを表示する方法の詳細については、「[ポップアップ メニューとしてのメニューの表示する](../windows/viewing-a-menu-as-a-pop-up-menu.md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご参照ください。  
  
 **必要条件**  
  
 Win32  
  
## 参照  
 [Connecting a Pop\-up Menu to Your Application](../Topic/Connecting%20a%20Pop-up%20Menu%20to%20Your%20Application.md)   
 [Menu Editor](../Topic/Menu%20Editor.md)