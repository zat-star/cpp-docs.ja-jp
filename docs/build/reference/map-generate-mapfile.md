---
title: "/MAP (マップ ファイルの生成) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/map"
  - "VC.Project.VCLinkerTool.MapFileName"
  - "VC.Project.VCLinkerTool.GenerateMapFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MAP リンカー オプション"
  - "生成 (マップ ファイルの) リンカー オプション"
  - "MAP リンカー オプション"
  - "-MAP リンカー オプション"
  - "mapfile リンカー オプション"
  - "マップ ファイル, 作成 (リンカーを)"
  - "マップ ファイル, 情報 (リンクされているプログラムに関する)"
  - "マップ ファイル, 指定 (ファイル名を)"
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /MAP (マップ ファイルの生成)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MAP[:filename]  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *filename*  
 ユーザー指定のマップ ファイル名。  既定の名前を置き換えます。  
  
## 解説  
 \/MAP オプションは、リンク時にマップ ファイルを生成します。  
  
 既定では、マップ ファイルは、プログラムのベース名に拡張子 .map が付いた名前になります。  *filename* \(省略可能\) を指定すると、既定のマップ ファイル名をオーバーライドできます。  
  
 マップ ファイルは、リンクするプログラムに関する次の情報が書き込まれたテキスト ファイルです。  
  
-   モジュール名。つまり、ファイルのベース名です。  
  
-   プログラム ファイルのヘッダーに書き込まれているタイムスタンプ。ファイル システムに書き込まれているタイムスタンプではありません。  
  
-   プログラム内のグループの一覧。各グループの先頭アドレス \(*section*:*offset* の形で表記\)、長さ、グループ名、およびクラスが記述されています。  
  
-   パブリック シンボルの一覧。各シンボルのアドレス \(*section*:*offset* の形で表記\)、シンボル名、フラット アドレス、およびそのシンボルを定義している .obj ファイルが記述されています。  
  
-   エントリ ポイント \(*section*:*offset* の形で表記\)。  
  
 [\/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md) オプションは、マップ ファイルに記述する追加情報を指定します。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[デバッグ\] プロパティ ページをクリックします。  
  
4.  \[マップ ファイルの作成\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)