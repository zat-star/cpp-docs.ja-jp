---
title: "Adding Formatting or Special Characters to a String | Microsoft Docs"
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
  - "special characters, adding to strings"
  - "ASCII characters, adding to strings"
  - "strings [C++], formatting"
  - "strings [C++], special characters"
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Adding Formatting or Special Characters to a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### 文字列に書式指定文字または特殊文字を追加するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)でアイコンをダブルクリックして、ストリング テーブルを開きます。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  変更する文字列を選択します。  
  
3.  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)で、下の一覧に示す任意の標準エスケープ シーケンスを \[Caption\] ボックスのテキストに追加し、**Enter** キーを押します。  
  
    |追加する文字|エスケープ シーケンス|  
    |------------|-----------------|  
    |改行|\\n|  
    |キャリッジ リターン|\\r|  
    |タブ|\\t|  
    |円記号 \(\\\)|\\\\|  
    |ASCII 文字|\\ddd \(8 進表記\)|  
    |警告 \(ベル\)|\\a|  
  
> [!NOTE]
>  ストリング エディターでは、一部の ASCII エスケープ文字セットがサポートされていません。  上の一覧に示す文字だけを使用できます。  
  
 共通言語ランタイムを対象とするマネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 **要件**  
  
 Win32  
  
## 参照  
 [String Editor](../mfc/string-editor.md)   
 [Strings \(ストリング\)](_win32_Strings)   
 [About Strings \(ストリングについて\)](_win32_About_Strings_cpp)