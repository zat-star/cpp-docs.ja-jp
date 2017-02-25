---
title: "/HEAP (ヒープ サイズの設定) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.HeapCommitSize"
  - "/heap"
  - "VC.Project.VCLinkerTool.HeapReserveSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/HEAP リンカー オプション"
  - "ヒープ割り当て, 設定 (ヒープ サイズを)"
  - "HEAP リンカー オプション"
  - "-HEAP リンカー オプション"
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /HEAP (ヒープ サイズの設定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/HEAP:reserve[,commit]  
```  
  
## 解説  
 \/HEAP オプションでは、ヒープ サイズをバイト単位で設定します。  このオプションは、.exe ファイルのビルドだけに使用します。  
  
 引数 *reserve* には、仮想メモリのヒープ領域に割り当てる総サイズを指定します。  既定では、ヒープ サイズは 1 MB になります。  指定した値は、4 バイト単位に切り上げられます。  
  
 引数 `commit` \(省略可能\) は、オペレーティング システムによって解釈が異なります。  Windows NT と Windows 2000 では、一度に確保する物理メモリ量です。  仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。  `commit` の値を大きく設定すると、アプリケーションでさらにヒープ領域が必要になった場合に実行時間を短縮できます。ただし、起動時に必要なメモリ量が増え、起動時間が長くなる場合があります。  
  
 引数 *reserve* と引数 `commit` の値は、10 進表記か C 言語表記で指定します。  
  
 この機能は、[HEAPSIZE](../../build/reference/heapsize.md) を使ったモジュール定義ファイルでも使用できます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[システム\] プロパティ ページをクリックします。  
  
4.  \[ヒープ コミット サイズの設定\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)