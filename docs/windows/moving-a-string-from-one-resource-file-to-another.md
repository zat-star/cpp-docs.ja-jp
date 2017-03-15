---
title: "Moving a String from One Resource File to Another | Microsoft Docs"
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
  - "strings [C++], moving between files"
  - "resource script files, moving strings"
  - "string editing, moving strings between resources"
  - "String editor, moving strings between files"
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Moving a String from One Resource File to Another
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### リソース スクリプト ファイルから別のリソース スクリプト ファイルに文字列を移動するには  
  
1.  両方の .rc ファイルのストリング テーブルを開きます。  詳細については、「[プロジェクトの外側にある \(スタンドアロン\) リソース スクリプト ファイルのオープン](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)」を参照してください。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  移動する文字列を右クリックし、ショートカット メニューの \[切り取り\] をクリックします。  
  
3.  移動先の \[ストリング エディター\] ウィンドウにカーソルを置きます。  
  
4.  文字列の移動先の .rc ファイルで右クリックし、ショートカット メニューの \[貼り付け\] をクリックします。  
  
    > [!NOTE]
    >  移動した文字列の ID または値が、移動先ファイルの既存の ID または値と競合したときは、移動した文字列の ID または値が変更されます。  同一の ID を持つ文字列が存在するときは、移動した文字列の ID が変更されます。  同一の値を持つ文字列が存在するときは、移動した文字列の値が変更されます。  
  
 共通言語ランタイムを対象とするマネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 **要件**  
  
 Win32  
  
## 参照  
 [String Editor](../mfc/string-editor.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [ウィンドウ レイアウトをカスタマイズする](../Topic/Customizing%20window%20layouts%20in%20Visual%20Studio.md)   
 [Strings \(ストリング\)](_win32_Strings)   
 [About Strings \(ストリングについて\)](_win32_About_Strings_cpp)