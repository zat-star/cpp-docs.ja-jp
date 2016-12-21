---
title: "かっこ付きのファイル名を含む | Microsoft Docs"
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
  - "C"
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# かっこ付きのファイル名を含む
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.8.2** インクルード可能なソース ファイルを見つけるための手段  
  
 山かっこで囲まれたファイル指定の場合、プリプロセッサは親ファイルのディレクトリを検索しません。  "親" ファイルとは、[\#include](../preprocessor/hash-include-directive-c-cpp.md) ディレクティブがあるファイルです。  代わりに、コンパイラ コマンド ラインで \/I の後に指定したディレクトリからファイル検索を開始します。  \/I オプションがない場合または失敗した場合、プリプロセッサは INCLUDE 環境変数を使用して、山かっこで囲まれたインクルード ファイルを検索します。  INCLUDE 環境変数には、セミコロン \(**;**\) で区切られた複数のパスを含めることができます。  複数のディレクトリが \/I オプションの一部として、または INCLUDE 環境変数内にある場合、プリプロセッサではそれらのディレクトリを表示されている順序で検索します。  
  
## 参照  
 [プリプロセス ディレクティブ](../Topic/Preprocessing%20Directives.md)