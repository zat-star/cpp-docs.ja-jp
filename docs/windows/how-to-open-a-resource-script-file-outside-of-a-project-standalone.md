---
title: "How to: Open a Resource Script File Outside of a Project (Standalone) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "rc files, viewing resources"
  - ".rc files, viewing resources"
  - "resource script files, viewing resources"
ms.assetid: bc350c60-178d-4c5d-9a7e-6576b0c936e4
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Open a Resource Script File Outside of a Project (Standalone)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.rc ファイル内のリソースは、プロジェクトを開かずに表示できます。  その場合、.rc ファイルはドキュメント ウィンドウに表示されます \(プロジェクト内で開く場合は [&#91;リソース ビュー&#93;](../windows/resource-view-window.md) ウィンドウに表示されます\)。  
  
> [!NOTE]
>  ファイルをスタンドアロンで \(プロジェクトの外側で\) 開いているときのみ使用できるコマンドがあるため、この違いは重要です。  たとえば、ファイルをプロジェクトの外側で開いているときのみ、別の形式や別のファイル名でファイルを保存できます \(ファイルをプロジェクト内で開いているときは、**\[名前を付けて保存\]** コマンドを使用できません\)。  
  
### プロジェクトの外部で .rc ファイルを開くには  
  
1.  **\[ファイル\]** メニューの **\[開く\]** を選択し、**\[ファイル\]** をクリックします。  
  
2.  **\[ファイルを開く\]** ダイアログ ボックスで、表示するリソース スクリプト ファイルまで移動し、そのファイルを強調表示して、**\[開く\]** をクリックします。  
  
    > [!NOTE]
    >  プロジェクトを先に開いた場合は \(**\[ファイル\]**、**\[開く\]**、**\[プロジェクト\]** の順に選択\)、一部のコマンドを使用できなくなります。  ファイルを "スタンドアロン" で開くと、プロジェクトを先に読み込むことなくファイルを開くことができます。  
  
 リソース ファイルをテキスト形式で開いて表示する方法については、「[リソース スクリプト \(.rc\) ファイルの編集](../windows/how-to-open-a-resource-script-file-in-text-format.md)」を参照してください。  
  
#### プロジェクトの外部で複数の .rc ファイルを開くには  
  
1.  2 つのリソース ファイルをスタンドアロンで開きます。  たとえば、Source1.rc と Source2.rc を開きます。  
  
    1.  **\[ファイル\]** メニューの **\[開く\]** を選択し、**\[ファイル\]** をクリックします。  
  
    2.  **\[ファイルを開く\]** ダイアログ ボックスで、最初に開くリソース スクリプト ファイル \(Source1.rc\) まで移動し、そのファイルを強調表示して、**\[開く\]** をクリックします。  
  
    3.  直前の手順を繰り返して、2 番目の .rc ファイル \(Source2.rc\) を開きます。  
  
         2 つの .rc ファイルが別個のドキュメント ウィンドウで開きました。  
  
2.  2 つの .rc ファイルを開いているときに、次の手順に従ってウィンドウを並べて表示すると、両方のファイルを同時に見ることができます。  
  
    -   **\[ウィンドウ\]** メニューの **\[水平タブ グループの新規作成\]** または **\[垂直タブ グループの新規作成\]** をクリックします。  
  
         または  
  
    -   一方の .rc ファイルを右クリックし、ショートカット メニューの **\[水平タブ グループの新規作成\]** または **\[垂直タブ グループの新規作成\]** をクリックします。  
  
> [!NOTE]
>  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
### 必要条件  
 Win32  
  
## 参照  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)