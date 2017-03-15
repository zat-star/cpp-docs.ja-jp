---
title: "Associating a Menu Command with an Accelerator Key | Microsoft Docs"
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
  - "keyboard shortcuts, menu association"
  - "commands, associating menu commands with accelerator keys"
  - "menu commands, associating with keyboard shortcuts"
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Associating a Menu Command with an Accelerator Key
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メニュー コマンドとキーボードの組み合わせで同じプログラム コマンドを発行したいと思うことはよくあります。 これを行うには、メニュー エディターを使用して、メニュー コマンドと、アプリケーションのアクセラレータ テーブル内のエントリに、同じリソース識別子を割り当てます。 次に、メニュー コマンドの[キャプション](../windows/menu-command-properties.md)を編集して、アクセラレータ キーの名前を表示します。  
  
### メニュー コマンドをアクセラレータ キーと関連付けるには  
  
1.  **メニュー** エディターで、目的のメニュー コマンドを選択します。  
  
2.  [プロパティ ウィンドウ](../Topic/Properties%20Window.md)で、アクセラレータ キーの名前を**キャプション** プロパティに追加します。  
  
    -   メニューのキャプションに続いて、タブ \(\\t\) のエスケープ シーケンスを入力し、すべてのメニューのアクセラレータ キーが左揃えされるようにします。  
  
    -   修飾キー \(**CTRL**, **ALT**, または **SHIFT**\)、およびそれに続いて正符号 \(**\+**\) と、追加キーの名前、文字、またはシンボルを入力します。  
  
         たとえば、**CTRL\+O** を **\[ファイル\]** メニューの **\[開く\]** コマンドに割り当てるには、メニュー コマンドの**キャプション**を変更し、次のようにします。  
  
        ```  
        &Open...\tCtrl+O   
        ```  
  
         メニュー エディターのメニュー コマンドは、入力する新しいキャプションを反映するよう更新されます。  
  
3.  **アクセラレータ** エディターで[アクセラレータ テーブル エントリ](../windows/adding-an-entry-to-an-accelerator-table.md)を作成し、メニュー コマンドと同じ識別子をそれに割り当てます。 使用するキーの組み合わせは、覚えやすいものにしてください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
 **要件**  
  
 Win32  
  
## 参照  
 [Adding Commands to a Menu](../Topic/Adding%20Commands%20to%20a%20Menu.md)   
 [Menu Editor](../Topic/Menu%20Editor.md)