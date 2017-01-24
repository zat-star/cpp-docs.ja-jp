---
title: "/OUT (出力ファイル名) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.OutputFile"
  - "/out"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/OUT C++ リンカー オプション"
  - "リンカー [C++], 出力ファイル"
  - "OUT リンカー オプション"
  - "-OUT リンカー オプション"
  - "出力ファイル, name リンカー オプション"
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /OUT (出力ファイル名)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/OUT:filename  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *filename*  
 ユーザー指定の出力ファイル名。  既定の名前を置き換えます。  
  
## 解説  
 \/OUT オプションは、リンカーで生成されるプログラムの既定の名前と場所をオーバーライドします。  
  
 既定では、出力ファイル名は、最初の .obj ファイルのベース名に拡張子 .exe か .dll を付けた名前になります。  
  
 このオプションは、マップ ファイルまたはインポート ライブラリの既定のベース名を制御します。  詳細については、「[\/MAP \(マップ ファイルの生成\)](../../build/reference/map-generate-mapfile.md)」および「[\/IMPLIB \(インポート ライブラリ名の設定\)](../Topic/-IMPLIB%20\(Name%20Import%20Library\).md)」を参照してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[全般\] プロパティ ページをクリックします。  
  
4.  \[出力ファイル\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)