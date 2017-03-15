---
title: "BSCMAKE リファレンス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".bsc ファイル, ビルド"
  - "ブラウザー情報ファイル (.bsc), ビルド"
  - "ブラウズ ウィンドウ"
  - "bsc ファイル, ビルド"
  - "BSCMAKE"
  - "BSCMAKE, リファレンス"
  - "Microsoft Browse Information Maintenance Utility (BSCMAKE.EXE)"
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# BSCMAKE リファレンス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!WARNING]
>  BSCMAKE は、現在も Visual Studio と共にインストールされていますが、IDE では使用されなくなりました。  Visual Studio 2008 以降、ブラウザーとシンボルの情報は、ソリューション フォルダー内の SQL Server の .sdf ファイルに自動的に格納されます。  
  
 Microsoft Browse Information Maintenance Utility \(BSCMAKE.EXE\) は、コンパイル時に作成された .sbr ファイルから、ブラウザー情報ファイル \(.bsc\) を作成します。  ブラウザー情報ファイルはオブジェクト ブラウザーで表示します。  オブジェクト ブラウザーの詳細については、「[オブジェクト ブラウザー内の移動](http://msdn.microsoft.com/ja-jp/53eb91aa-08c6-4299-8e3c-a877ae8d0c55)」を参照してください。  
  
 プログラムをビルドするときに、BSCMAKE を使用してファイルをビルドすれば、プログラムのブラウザー情報ファイルを自動的に作成できます。  Visual C\+\+ 開発環境でブラウザー情報ファイルを作成する場合は、BSCMAKE の実行方法を知る必要はありません。  ただし、このトピックを読めば、利用可能な選択肢を理解することができます。  
  
 開発環境の外部でプログラムをビルドする場合は、その環境で確認することができるカスタム .bsc ファイルを作成できます。  コンパイル中に作成した .sbr ファイル上で BSCMAKE を実行します。  
  
> [!NOTE]
>  このツールは、[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] コマンド プロンプトからのみ開始できます。  システム コマンド プロンプトやエクスプローラーからは開始できません。  
  
 ここでは、次のトピックについて説明します。  
  
-   [ブラウザー情報ファイルのビルド : 概要](../../build/reference/building-browse-information-files-overview.md)  
  
-   [.bsc ファイルのビルド](../../build/reference/building-a-dot-bsc-file.md)  
  
-   [BSCMAKE コマンド ライン](../../build/reference/bscmake-command-line.md)  
  
-   [BSCMAKE コマンド ファイル](../../build/reference/bscmake-command-file-response-file.md)  
  
-   [BSCMAKE オプション](../Topic/BSCMAKE%20Options.md)  
  
-   [BSCMAKE 終了コード](../Topic/BSCMAKE%20Exit%20Codes.md)  
  
## 参照  
 [C と C\+\+ のビルド ツール](../Topic/C-C++%20Build%20Tools.md)