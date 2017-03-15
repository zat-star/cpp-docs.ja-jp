---
title: "BSCMAKE コマンド ライン | Microsoft Docs"
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
  - "BSCMAKE, コマンド ライン"
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# BSCMAKE コマンド ライン
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BSCMAKE を実行するには、次のコマンド ライン構文を使用します。  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 オプションは、コマンド ラインの `options` フィールドだけで指定できます。  
  
 *sbrfiles* フィールドでは、コンパイラまたはアセンブラーで作成された .sbr ファイルを指定します。  複数の .sbr ファイルの名前は、スペースまたはタブで区切ります。  拡張子は必ず指定します。既定の拡張子はありません。  ファイル名では、パスを指定できます。また、オペレーティング システムのワイルドカード \(\* および ?\) も使用できます。  
  
 インクリメンタル ビルドでは、最初のビルドには含まれていない新しい .sbr ファイルを指定できます。  ブラウザー情報ファイルですべての情報を維持するには、.bsc ファイルを作成するために使用したすべての .sbr ファイル \(切り捨てられたファイルを含む\) を指定する必要があります。  .sbr ファイルを省くと、そのファイルの情報がブラウザー情報ファイルから削除されます。  
  
 完全ビルドの場合は、切り捨てられている .sbr ファイルを指定しないでください。  完全ビルドでは、指定されたすべての .sbr ファイルからの情報が必要です。  完全ビルドを実行する前には、プロジェクトを再コンパイルし、空のファイルで新しい .sbr ファイルを作成します。  
  
 BSCMAKE を実行して 3 つの .sbr ファイルから MAIN.bsc というファイルをビルドする場合は、次のコマンドを実行します。  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 関連情報については、「[BSCMAKE コマンド ファイル \(応答ファイル\)](../../build/reference/bscmake-command-file-response-file.md)」および「[BSCMAKE オプション](../Topic/BSCMAKE%20Options.md)」を参照してください。  
  
## 参照  
 [BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)