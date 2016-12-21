---
title: "/INCLUDE (シンボルの明示的な参照) | Microsoft Docs"
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
  - "/include"
  - "VC.Project.VCLinkerTool.ForceSymbolReferences"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/INCLUDE リンカー オプション"
  - "シンボル参照の強制リンカー オプション"
  - "INCLUDE リンカー オプション"
  - "-INCLUDE リンカー オプション"
  - "シンボルの明示的な参照 (リンカーの)"
  - "シンボル, 追加 (シンボル テーブルに)"
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /INCLUDE (シンボルの明示的な参照)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/INCLUDE:symbol  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 `symbol`  
 シンボルをシンボル テーブルに追加します。  
  
## 解説  
 \/INCLUDE オプションは、指定されたシンボルをシンボル テーブルに追加します。  
  
 複数のシンボルを指定する場合は、各シンボルの間をコンマ \(,\)、セミコロン \(;\)、またはスペースのいずれかで区切ります。  コマンド ラインでは、シンボルごとに \/INCLUDE:`symbol` を指定します。  
  
 シンボルは、指定した `symbol` が定義されているオブジェクトをプログラムに加えると、解決されます。  この機能を使うと、本来プログラムにリンクされないライブラリ オブジェクトでも取り込むことができます。  
  
 このオプションは [\/OPT:REF](../../build/reference/opt-optimizations.md) に優先し、\/OPT:REF で削除の対象として指定されていても、そのオブジェクトは削除されません。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[入力\] プロパティ ページをクリックします。  
  
4.  \[シンボル参照の強制\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)