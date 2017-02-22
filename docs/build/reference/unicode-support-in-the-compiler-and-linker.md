---
title: "コンパイラおよびリンカーでの Unicode のサポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.UseUnicodeResponseFiles"
  - "VC.Project.VCLibrarianTool.UseUnicodeResponseFiles"
  - "VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles"
  - "VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unicode, Visual C++"
ms.assetid: acc1d322-56b9-4696-a30e-2af891a4e288
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラおよびリンカーでの Unicode のサポート
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、Visual C\+\+ ビルド ツールでの Unicode のサポートについて説明します。  
  
 ファイル名  
 コマンド ラインまたはコンパイラ ディレクティブ \(\#include など\) で指定されるファイル名に、Unicode 文字を含めることができるようになりました。  
  
 ソース コード ファイル  
 識別子、マクロ、文字列リテラル、文字リテラル、およびコメントで、Unicode 文字がサポートされるようになりました。また、ユニバーサル文字名もサポートされるようになりました。  
  
 Unicode は、次のエンコーディングのソース コード ファイルに入力できます。  
  
-   BOM \(Byte Order Mark\) 付き、または BOM なしの UTF\-16 リトル エンディアン。  
  
-   BOM 付き、または BOM なしの UTF\-16 ビッグ エンディアン。  
  
-   BOM 付きの UTF\-8  
  
 出力  
 コンパイル時に、コンパイラは UTF\-16 で診断をコンソールに出力します。コンソールに表示できる文字は、コンソール ウィンドウのプロパティによって決まりますファイルにリダイレクトされるコンパイラ出力は、現在の ANSI コンソール コードページになります。  
  
 リンカー応答ファイルおよび .DEF ファイル  
 応答ファイルおよび DEF ファイルは、BOM 付きの UTF\-16、または ANSI にできます。以前は ANSI だけがサポートされていました。  
  
 .asm ダンプおよび .cod ダンプ  
 .asm ダンプおよび .cod ダンプは、MASM との互換性のために、既定で ANSI になっています。UTF\-8 を出力するには \/FAu を使用します。\/FAs を指定した場合、混在したソースが直接出力されるため、文字が正しく表示されない可能性があります。たとえば、ソース コードが UTF\-8 の場合に \/FAsu を指定しなかった場合などがこれにあたります。  
  
 開発環境で Unicode ファイル名を有効にするには \(「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照\)、適切なツールを選択するか、既定で有効になっている **\[UNICODE 応答ファイルの使用\]** プロパティを選択します。  この既定値を変更するのは、Unicode をサポートしていないコンパイラを使用するように開発環境を変更する場合などです。  
  
## 参照  
 [コマンド ラインでのビルド](../Topic/Building%20on%20the%20Command%20Line.md)