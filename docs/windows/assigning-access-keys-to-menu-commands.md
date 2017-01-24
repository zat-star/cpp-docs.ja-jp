---
title: "Assigning Access Keys to Menu Commands | Microsoft Docs"
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
  - "access keys [C++], checking"
  - "menus, shortcut keys"
  - "keyboard shortcuts [C++], command assignments"
  - "access keys [C++], assigning"
  - "mnemonics, adding to menus"
  - "keyboard shortcuts [C++], uniqueness checking"
  - "mnemonics, uniqueness checking"
  - "Check Mnemonics command"
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assigning Access Keys to Menu Commands
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メニューとメニュー コマンドにアクセス キー \(ユーザーがキーボードを使ってメニューを選択できるようにするニーモニック\) を割り当てることができます。  
  
### メニュー コマンドにアクセス \(ショートカット\) キーを割り当てるには  
  
1.  メニュー名やコマンド名の文字の前にアンパサンド \(**&**\) を入力し、対応するアクセス キーとしてその文字を指定します。 たとえば、"&File" は ALT\+F を、Microsoft Windows で作成されるアプリケーションの \[File\] メニューのショートカット キーとして設定します。  
  
     メニュー項目は、文字の 1 つがショートカット キーに割り当てられている表示可能キューを提供します。 アンパーサンドに続く文字は、下線付きで表示されます \(オペレーティング システムによって異なる\)。  
  
    > [!NOTE]
    >  メニューを右クリックし、ショートカット メニューから **\[ニーモニックの確認\]** を選択して、メニューのすべてのアクセスキーが一意であることを確認してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
 要件  
  
 Win32  
  
## 参照  
 [Menu Editor](../Topic/Menu%20Editor.md)