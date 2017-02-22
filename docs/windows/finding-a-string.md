---
title: "Finding a String | Microsoft Docs"
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
  - "strings [C++], searching"
  - "strings [C++]"
ms.assetid: c2497173-f356-4f77-97d6-f0ac41782510
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Finding a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ストリング テーブル内の 1 つ以上の文字列を検索し、\[編集\] メニューの \[ファイル内の検索\] で[正規表現](../Topic/Using%20Regular%20Expressions%20in%20Visual%20Studio.md)を使用して、パターンに一致するすべての文字列を検索できます。  
  
### ストリング テーブルの文字列を検索するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)でアイコンをダブルクリックして、ストリング テーブルを開きます。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  \[編集\] メニューの \[検索と置換\] をクリックし、\[検索\] をクリックします。  
  
3.  \[検索する文字列\] ボックスの一覧から以前の検索文字列を選択するか、または検索するキャプション テキストや文字列のリソース識別子を入力します。  
  
4.  \[検索\] オプションのいずれかを選択します。  
  
5.  **\[次を検索\]** をクリックします。  
  
    > [!TIP]
    >  ファイルの検索時に正規表現を使用するには、\[ファイル内の検索\] を使用します。  一致するパターンの正規表現を入力するか、または \[検索する文字列\] ボックスの右のボタンをクリックして検索の正規表現の一覧を表示します。  この一覧で正規表現を選択すると、\[検索する文字列\] ボックスの検索文字列として設定されます。  正規表現を使用するときは、\[条件\] チェック ボックスをオンにし、\[正規表現\] を選択してください。  
  
 共通言語ランタイムを対象とするマネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 **要件**  
  
 Win32  
  
## 参照  
 [String Editor](../mfc/string-editor.md)   
 [Strings \(ストリング\)](_win32_Strings)   
 [About Strings \(ストリングについて\)](_win32_About_Strings_cpp)