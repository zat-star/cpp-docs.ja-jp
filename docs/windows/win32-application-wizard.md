---
title: "Win32 アプリケーション ウィザード | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.win32.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Win32 アプリケーション ウィザード"
  - "Win32 プロジェクト ウィザード"
ms.assetid: 5d7b3a5e-8461-479a-969a-67b7883725b9
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Win32 アプリケーション ウィザード
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ の Win32 アプリケーション ウィザードを使用すると、以下の表の見出しに示す 4 種類のプロジェクトを作成できます。 いずれの場合でも、開くプロジェクトの種類に応じて追加のオプションを指定できます。 次の表では、使用できるオプションをアプリケーション タイプ別に示します。  
  
|アプリケーションの種類|コンソール アプリケーション|実行可能 \(Windows\) アプリケーション|ダイナミック リンク ライブラリ|スタティック ライブラリ|  
|-----------------|--------------------|-------------------------------|----------------------|------------------|  
|**空のプロジェクト**|○|○|○|Ｘ|  
|**シンボルのエクスポート**|Ｘ|Ｘ|○|Ｘ|  
|**プリコンパイル済みヘッダー**|Ｘ|Ｘ|Ｘ|○|  
|**ATL サポート**|○|Ｘ|Ｘ|Ｘ|  
|**MFC サポート**|○|Ｘ|Ｘ|○|  
  
## 概要  
 このウィザード ページでは、作成する Win32 アプリケーションの現在のプロジェクト設定が示されます。 既定では、以下のオプションが設定されています。  
  
-   プロジェクトが Windows アプリケーションである。  
  
-   プロジェクトが空ではない。  
  
-   プロジェクトにエクスポート シンボルが含まれない。  
  
-   プロジェクトでプリコンパイル済みヘッダー ファイルを使用しない。このオプションを使用できるのはスタティック ライブラリ プロジェクトだけです。  
  
-   プロジェクトに MFC または ATL のサポートが含まれない。  
  
 これらの既定値を変更するには、ウィザードの左の列にある [&#91;アプリケーションの設定&#93;](../Topic/Application%20Settings,%20Win%2032%20Project%20Wizard.md) タブを使用します。  
  
 Windows デスクトップ アプリケーションを作成したら、[汎用](../ide/generic-cpp-class-wizard.md)コード ウィザードを使用して汎用 C\+\+ クラスを追加できます。 HTML ファイル、ヘッダー ファイル、リソース、テキスト ファイルなど、その他の項目も追加できます。  
  
> [!NOTE]
>  ATL クラスは追加できません。また、MFC クラスを追加できるのは、MFC をサポートするタイプの Windows デスクトップ アプリケーションだけです。上の表を参照してください。  
  
 ウィザードでプロジェクト用に作成されるファイルは、**ソリューション エクスプローラー**で表示できます。 ウィザードでプロジェクト用に作成されるファイルの詳細については、プロジェクトが生成する ReadMe.txt ファイルを参照してください。 ファイルの種類の詳細については、「[Visual C\+\+ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)」を参照してください。  
  
## 参照  
 [空の Windows デスクトップ アプリケーションを作成する](../windows/creating-an-empty-windows-desktop-application.md)   
 [Visual C\+\+ プロジェクトの種類](../ide/visual-cpp-project-types.md)