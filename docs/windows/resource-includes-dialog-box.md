---
title: "[リソース インクルード] ダイアログ ボックス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resourceincludes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "[リソース インクルード] ダイアログ ボックス"
  - "rc ファイル、ストレージの変更"
  - "シンボル ヘッダー ファイルの変更"
  - "ソース コードのコンパイル、リソースを含む"
  - ".rc ファイル、ストレージの変更"
  - "シンボル ヘッダー ファイル、読み取り専用"
  - "シンボル、シンボル ヘッダー ファイル"
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# [リソース インクルード] ダイアログ ボックス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\[リソース ファイルのインクルード\]** ダイアログ ボックスを使用して、環境の通常の動作形態を変更することができます。通常は、すべてのリソースがプロジェクト .rc ファイルに格納され、すべての[シンボル](../mfc/symbols-resource-identifiers.md)が Resource.h に格納されます。  
  
 **\[リソース ファイルのインクルード\]** ダイアログ ボックスを開くには、[リソース ビュー](../windows/resource-view-window.md)で .rc ファイルを右クリックし、ショートカット メニューで **\[リソース ファイルのインクルード\]** を選択します。  
  
 **シンボル用のヘッダー ファイル**  
 リソース ファイルのシンボル定義が格納されているヘッダー ファイルの名前を変更することができます。  詳細については、「[シンボル ヘッダー ファイル名の変更](../windows/changing-the-names-of-symbol-header-files.md)」を参照してください。  
  
 **読み取り専用ヘッダー ファイル**  
 編集セッション中に変更してはいけないシンボルが格納されているヘッダー ファイルをインクルードすることができます。  たとえば、いくつかのプロジェクト間で共有されるシンボル ファイルをインクルードできます。  MFC の .h ファイルをインクルードすることもできます。  詳細については、「[共有シンボル \(読み取り専用\) または計算型シンボルのインクルード](../windows/including-shared-read-only-or-calculated-symbols.md)」を参照してください。  
  
 **コンパイル時に追加するファイル**  
 メイン リソース ファイルのリソースとは個別に作成および編集されたリソース ファイルをインクルードしたり、コンパイル時ディレクティブ \(たとえば、条件付きでリソースをインクルードするディレクティブなど\) を含めたり、カスタム形式のリソースを含めたりすることができます。  また、\[コンパイル時に追加するファイル\] ボックスを使用して、標準 MFC リソース ファイルをインクルードすることもできます。  詳細については、「[コンパイル時にリソースをインクルードする](../Topic/How%20to:%20Include%20Resources%20at%20Compile%20Time.md)」を参照してください。  
  
> [!NOTE]
>  これらのテキスト ボックス内のエントリは、.rc ファイル内にそれぞれ  `TEXTINCLUDE 1`、`TEXTINCLUDE 2`、および `TEXTINCLUDE 3` でマークされて存在します。  詳細については、「[テクニカル ノート 35: Visual C\+\+ における複数のリソース ファイルとヘッダー ファイルの使用](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)」を参照してください。  
  
 **\[リソース ファイルのインクルード\]** ダイアログ ボックスを使用してリソース ファイルを変更した後、変更内容を有効にするには、.rc ファイルを閉じてから再度開く必要があります。  詳細については、「[コンパイル時にリソースをインクルードする](../Topic/How%20to:%20Include%20Resources%20at%20Compile%20Time.md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
## 必要条件  
 Win32  
  
## 参照  
 [How to: Specify Include Directories for Resources](../windows/how-to-specify-include-directories-for-resources.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)