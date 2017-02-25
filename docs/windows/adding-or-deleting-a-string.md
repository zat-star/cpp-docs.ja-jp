---
title: "Adding or Deleting a String | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.string"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strings [C++], adding to string tables"
  - "string tables, deleting strings"
  - "strings [C++], deleting in string tables"
  - "string tables, adding strings"
ms.assetid: 077077b4-0f4b-4633-92d6-60b321164cab
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Adding or Deleting a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ストリング エディターを使用すると、ストリング テーブルに新規エントリをすばやく追加できます。  新規の文字列はテーブルの最後に配置され、その次の使用可能な識別子が与えられます。  必要に応じて ID、値、または Caption の各プロパティを [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)で編集できます。  
  
 ストリング エディターでは、既に使われている ID の使用が回避されます。  既に使われている ID を選択した場合は、ストリング エディターによって通知され、IDS\_STRING58113 などの一意な汎用 ID が割り当てられます。  
  
### ストリング テーブルのエントリを追加するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)でアイコンをダブルクリックして、ストリング テーブルを開きます。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  ストリング テーブルで右クリックし、ショートカット メニューの \[新しい文字列\] をクリックします。  
  
3.  ストリング エディターで、\[ID\] ボックスの一覧の ID を選択するか、または ID を直接入力します。  
  
4.  必要に応じて \[値\] を編集します。  
  
5.  \[Caption\] にエントリを入力します。  
  
    > [!NOTE]
    >  Windows ストリング テーブルでは、null 文字列は許可されません。  ストリング テーブルで null 文字列のエントリを作成すると、"このテーブル項目に文字列を入力してください。" というメッセージが表示されます。  
  
### ストリング テーブルのエントリを削除するには  
  
1.  削除するエントリを選択します。  
  
2.  **\[編集\]** メニューの **\[削除\]** をクリックします。  
  
 または  
  
-   削除する文字列を右クリックし、ショートカット メニューの \[削除\] をクリックします。  
  
 または  
  
-   **Del** キーを押します。  
  
 共通言語ランタイムを対象とするマネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 **要件**  
  
 Win32  
  
## 参照  
 [String Editor](../mfc/string-editor.md)   
 [Strings \(ストリング\)](_win32_Strings)   
 [About Strings \(ストリングについて\)](_win32_About_Strings_cpp)