---
title: "/SWAPRUN (リンカー出力をスワップ ファイルに読み込む) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.SwapRunFromNet"
  - "/swaprun"
  - "VC.Project.VCLinkerTool.SwapRunFromCD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SWAPRUN リンカー オプション"
  - "ファイル [C++], LINK"
  - "LINK ツール [C++], 出力"
  - "リンカー [C++], コピー (出力をスワップ ファイルに)"
  - "出力ファイル, リンカー"
  - "スワップ ファイル (リンカー出力用の)"
  - "SWAPRUN リンカー オプション"
  - "-SWAPRUN リンカー オプション"
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /SWAPRUN (リンカー出力をスワップ ファイルに読み込む)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SWAPRUN:{NET|CD}  
```  
  
## 解説  
 \/SWAPRUN オプションは、リンカー出力をスワップ ファイルにコピーし、そのコピーからイメージを実行するように、オペレーティング システムに指示します。  これは Windows NT 4.0 以降の機能です。  
  
 NET を指定すると、オペレーティング システムは、まずネットワークからのバイナリ イメージをスワップ ファイルにコピーし、そのファイルからイメージを読み込みます。  このオプションは、ネットワーク上でアプリケーションを実行するときに便利です。  CD を指定すると、オペレーティング システムは、リムーバブル ディスク上のイメージをページ ファイルにコピーし、そのファイルからイメージを読み込みます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[システム\] プロパティ ページをクリックします。  
  
4.  次のいずれかのプロパティを変更します。  
  
    -   **\[CD からスワップ実行\]**  
  
    -   **\[ネットワークからスワップ実行\]**  
  
### このリンカーをコードから設定するには  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> プロパティを参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)