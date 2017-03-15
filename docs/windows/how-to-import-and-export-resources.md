---
title: "How to: Import and Export Resources | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.resvw.resource.importing"
  - "vc.resvw.resource.importing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], exporting"
  - "graphics [C++], exporting"
  - "graphics [C++], importing"
  - "resources [Visual Studio], importing"
  - "bitmaps [C++], importing and exporting"
  - "toolbars [C++], importing"
  - "images [C++], importing"
  - "toolbars [C++], exporting"
  - "cursors [C++], importing and exporting"
  - "images [C++], exporting"
ms.assetid: 3c9329dc-dcb8-4edd-a600-78e3e572bd89
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# How to: Import and Export Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

グラフィカル リソース \(ビットマップ、アイコン、カーソル、ツール バー\)、HTML ファイル、および Visual C\+\+ で使用するためのカスタム リソースをインポートすることができます。  Visual C\+\+ プロジェクトから、同じ種類のファイルを別のファイルにエクスポートして、開発環境の外部で使用することができます。  
  
> [!NOTE]
>  アクセラレータ、ダイアログ ボックス、文字列テーブルなどのリソースの種類は、スタンドアロンのファイルの種類ではないため、インポートまたはエクスポートすることはできません。  
  
### 1 つのリソースを現在のリソース ファイルにインポートするには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)で、リソースを追加するリソース スクリプト \(\*.rc\) ファイルのノードを右クリックします。  
  
2.  ショートカット メニューの **\[インポート\]** をクリックします。  
  
3.  インポートするビットマップ \(.bmp\)、アイコン \(.ico\)、カーソル \(.cur\)、Html ファイル \(.htm\)、またはその他のファイルを見つけてそのファイル名を選択します。  
  
4.  **\[OK\]** をクリックして、**リソース** ビューで選択したファイルにリソースを追加します。  
  
    > [!NOTE]
    >  どの種類のリソースを選択した場合も、インポート プロセスは同じように実行されます。  インポートされたリソースは、そのリソースの種類の適切なノードに自動的に追加されます。  
  
### \(Visual C\+\+ の外部で使用するために\) ビットマップ、アイコン、またはカーソルを別のファイルとしてエクスポートするには  
  
1.  **リソース** ビューで、エクスポートするリソースを右クリックします。  
  
2.  ショートカット メニューの **\[エクスポート\]** をクリックします。  
  
3.  **\[リソースのエクスポート\]** ダイアログ ボックスで、現在のファイル名を受け入れるか、新しい名前を入力します。  
  
4.  ファイルを保存するフォルダーに移動し、**\[エクスポート\]** をクリックします。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 必要条件  
  
 Win32  
  
## 参照  
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)