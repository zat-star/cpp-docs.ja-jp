---
title: "/w、/Wn、/WX、/Wall、/wln、/wdn、/wen、/won (警告レベル) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.DisableSpecificWarnings"
  - "VC.Project.VCCLCompilerTool.WarningLevel"
  - "VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings"
  - "VC.Project.VCCLCompilerTool.WarnAsError"
  - "VC.Project.VCCLWCECompilerTool.WarnAsError"
  - "/wx"
  - "VC.Project.VCCLWCECompilerTool.WarningLevel"
  - "/wall"
  - "VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors"
  - "/Wv"
  - "/w0"
  - "/w1"
  - "/w2"
  - "/w3"
  - "/w4"
  - "/wd"
  - "/we"
  - "/wo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/w コンパイラ オプション"
  - "/W0 コンパイラ オプション [C++]"
  - "/W1 コンパイラ オプション [C++]"
  - "/W2 コンパイラ オプション [C++]"
  - "/W3 コンパイラ オプション [C++]"
  - "/W4 コンパイラ オプション [C++]"
  - "/Wall コンパイラ オプション [C++]"
  - "/wd コンパイラ オプション [C++]"
  - "/we コンパイラ オプション [C++]"
  - "/wo コンパイラ オプション [C++]"
  - "/WX コンパイラ オプション [C++]"
  - "w コンパイラ オプション [C++]"
  - "-w コンパイラ オプション [C++]"
  - "W0 コンパイラ オプション [C++]"
  - "-W0 コンパイラ オプション [C++]"
  - "W1 コンパイラ オプション [C++]"
  - "-W1 コンパイラ オプション [C++]"
  - "W2 コンパイラ オプション [C++]"
  - "-W2 コンパイラ オプション [C++]"
  - "W3 コンパイラ オプション [C++]"
  - "-W3 コンパイラ オプション [C++]"
  - "W4 コンパイラ オプション [C++]"
  - "-W4 コンパイラ オプション [C++]"
  - "Wall コンパイラ オプション [C++]"
  - "-Wall コンパイラ オプション [C++]"
  - "警告レベル コンパイラ オプション"
  - "警告, エラーとしてのコンパイラ オプション"
  - "wd コンパイラ オプション [C++]"
  - "-wd コンパイラ オプション [C++]"
  - "we コンパイラ オプション [C++]"
  - "-we コンパイラ オプション [C++]"
  - "wo コンパイラ オプション [C++]"
  - "-wo コンパイラ オプション [C++]"
  - "WX コンパイラ オプション [C++]"
  - "-WX コンパイラ オプション [C++]"
ms.assetid: d6bc7bf5-c754-4879-909c-8e3a67e2629f
caps.latest.revision: 21
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /w、/Wn、/WX、/Wall、/wln、/wdn、/wen、/won (警告レベル)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラが特定のコンパイルの警告を生成する方法を指定します。  
  
## 構文  
  
```  
/w  
/Wn  
/WX  
/Wall  
/wln  
/wdn  
/wen  
/won  
```  
  
## 解説  
 これらのオプションおよび関連する引数の説明を次の表に示します。  
  
|オプション|説明|  
|-----------|--------|  
|**\/w**|すべてのコンパイラ警告を無効にします。|  
|**\/W** `n`|コンパイラで生成される警告のレベルを指定します。  `n` には、警告レベル 0 ～ 4 を指定できます。<br /><br /> -   レベル 0 は、すべての警告を無効にします。<br />-   レベル 1 は、重大な警告を表示します。  レベル 1 は既定の設定です。<br />-   レベル 2 は、レベル 1.より重大度レベル 1 のすべての警告と、警告が表示されます。<br />-   レベル 3 は、稼動用に推奨されるすべてのレベル 2 の警告に加えて、そのほかの警告をすべて表示します。<br />-   レベル 4 は、レベル 3 のすべての警告と情報の警告が表示されます。  これはリント形式の警告は使用しない場合は、このオプションを使用することをお勧めします。  ただし、新しいプロジェクトの場合は、すべてのコンパイルで `/W4` を使用するのが最適である可能性がある; これを使用すると、見つかりにくいコードの欠陥が最小限になります。|  
|**\/Wall**|—例、既定で無効になっている警告の… \/W4 に含まれない \/W4 のすべての警告と他の警告が表示されます。  「[Compiler Warnings That Are Off by Default](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。|  
|**\/WX**|すべてのコンパイラ警告をエラーとして扱います。  新規プロジェクトの場合は、すべてのコンパイルで **\/WX** を使用するのが最適です。すべての警告を解決すると、見つかりにくいコードの欠陥が最小限になります。<br /><br /> リンカーにも **\/WX** オプションがあります。  詳細については、「[\/WX \(リンカー警告をエラーとして扱う\)](../../build/reference/wx-treat-linker-warnings-as-errors.md)」を参照してください。|  
|**\/w** `ln`|特定の警告のレベルを指定します。  最初のパラメーターは警告レベルを設定し \(**\/W**`n` と同じ\)、2 番目のパラメーターは実際の警告番号です。<br /><br /> たとえば、`/w14326` と指定すると、C4326 をレベル 1 の警告として生成します。|  
|**\/wd** `n`|`n`で指定したコンパイラの警告を無効にします。<br /><br /> たとえば、`/wd4326` と指定すると、コンパイラの警告 C4326 が無効になります。|  
|**\/we** `n`|エラーとして扱う `n`で指定したコンパイラの警告を表示します。<br /><br /> たとえば、`/we4326` と指定すると、警告番号 C4326 をエラーとしてフラグ設定します。|  
|**\/wo** `n`|`n`で指定したコンパイラの警告の一度だけエラーを報告します。<br /><br /> たとえば、`/wo4326` は一度だけ警告 C4326 を報告します。|  
  
 **\/w** オプションを 1 回使用してプリコンパイル済みヘッダー \([\/Yc \(プリコンパイル済みヘッダー ファイルの作成\)](../../build/reference/yc-create-precompiled-header-file.md)\) を作成する場合は、プリコンパイル済みヘッダー \([\/Yu \(プリコンパイル済みヘッダー ファイルの使用\)](../../build/reference/yu-use-precompiled-header-file.md)\) の使用により、**\/w** 同じオプションも有効です。  コマンド ラインの **\/w** 別のオプションを使用して、プリコンパイル済みヘッダーに設定する **\/w** をオーバーライドできます。  
  
 ソース コードのプラグマ ディレクティブは、**\/w** オプションの影響を受けません。  
  
 、コンパイル時に報告される警告レベルを制御するために [warning](../../preprocessor/warning.md) を使用できます。  
  
 [ビルド エラーのドキュメント](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) は意図したとおりに警告や警告レベルについて説明し、特定のステートメントがなぜ使用しない可能性があるかを示します。  
  
### Visual Studio の開発環境でコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** を選択します。  
  
3.  **\[全般\]** プロパティ ページで、**\[Warning Level\]** または **\[警告をエラーとして処理\]** のプロパティを変更します。  
  
4.  **\[詳細\]** プロパティ ページで、**\[指定の警告を無効にする\]** のプロパティを変更します。  
  
5.  残りのオプションについては、**\[コマンド ライン\]** プロパティ ページで、**\[追加オプション\]** ボックスにコンパイラ オプションを入力します。  
  
### コンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>」、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>」、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A>」、および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)