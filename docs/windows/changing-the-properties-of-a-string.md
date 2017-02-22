---
title: "Changing the Properties of a String | Microsoft Docs"
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
  - "resource identifiers, string properties"
  - "string tables, changing strings"
  - "strings [C++], properties"
ms.assetid: 0a220434-f444-4405-9a64-d28d6b965687
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Changing the Properties of a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 文字列または文字列の識別子を変更するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)でアイコンをダブルクリックして、ストリング テーブルを開きます。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  編集する文字列を選択し、**\[ID\]** 列、\[値\] 列、または **\[Caption\]** 列をダブルクリックします。  以下の操作を行うことができます。  
  
    -   \[ID\] ボックスの一覧の ID を選択するか、または ID を直接入力します。  
  
    -   \[値\] 列に異なる数字を入力します。  
  
    -   \[Caption\] 列に変更内容を入力します。  
  
        > [!NOTE]
        >  文字列のプロパティは [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)でも編集できます。  
  
 共通言語ランタイムを対象とするマネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 **要件**  
  
 Win32  
  
## 参照  
 [String Editor](../mfc/string-editor.md)   
 [Strings \(ストリング\)](_win32_Strings)   
 [About Strings \(ストリングについて\)](_win32_About_Strings_cpp)