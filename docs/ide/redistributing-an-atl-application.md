---
title: "ATL アプリケーションの再配布 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "[ATL], 再配布"
  - "OLE DB テンプレート, 再配布"
  - "再配布 (ATL を)"
  - "再頒布 (OLE DB テンプレートを)"
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ATL アプリケーションの再配布
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio 2012 以降の Active Template Library \(ATL\) はヘッダーのみのライブラリです。  ATL プロジェクトには、ATL オプションへの動的リンクはありません。  再配布可能 ATL ライブラリは必要ありません。  
  
 ATL 実行可能アプリケーションを再配布する場合は、次のコマンドを実行して、.exe ファイルとそのすべてのコントロールを登録する必要があります。  
  
```  
filename /regserver  
  
```  
  
 `filename` は実行可能ファイルの名前です。  
  
 Visual Studio 2010 では、MinDependency または MinSize 構成用に ATL プロジェクトをビルドできます。  MinDependency 構成は、**\[全般\]** プロパティ ページの **\[ATL の使用\]** プロパティを **\[ATL に静的にリンク\]** に設定し、**\[コード生成\]** プロパティ ページ \(\[C\/C\+\+\] フォルダー\) の **\[ランタイム タイブラリ\]** プロパティを **\[マルチスレッド \(\/MT\)\]** に設定した場合です。  
  
 MinSize 構成は、**\[全般\]** プロパティ ページの **\[ATL の使用\]** プロパティを **\[ATL に動的にリンク\]** に設定し、**\[コード生成\]** プロパティ ページ \(\[C\/C\+\+\] フォルダー\) の **\[ランタイム タイブラリ\]** プロパティを **\[マルチスレッド DLL \(\/MD\)\]** に設定した場合です。  
  
 MinSize を使用すると、出力ファイルは可能な範囲で最小になりますが、ターゲット コンピューターに ATL100.dll と Msvcr100.dll \(**\[マルチスレッド DLL \(\/MD\)\]** オプションを選択した場合\) が必要になります。  すべての ATL 機能を使用できるようにするために、ATL100.dll をターゲット コンピューターに登録する必要があります。  ATL100.dll には ANSI および Unicode エクスポートが含まれています。  
  
 ATL または OLE DB テンプレート プロジェクトを MinDependency ターゲット用にビルドした場合、ターゲット コンピューターへの ATL100.dll のインストールと登録は不要ですが、プログラム イメージが大きくなります。  
  
 OLE DB テンプレート アプリケーションを再配布する場合は、ターゲット コンピューターに最新バージョンの Microsoft Data Access Components \(MDAC\) ファイルが必要です。  詳細については、「[データベース サポート ファイルの再頒布](../ide/redistributing-database-support-files.md)」を参照してください。  
  
## 参照  
 [Visual C\+\+ ファイルの再配布](../Topic/Redistributing%20Visual%20C++%20Files.md)