---
title: "環境変数 LINK | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "環境変数 [C++], LINK"
  - "LIB 環境変数"
  - "LINK ツール [C++], 環境変数"
  - "変数, 環境"
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 環境変数 LINK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK ツールでは、次の環境変数を使用します。  
  
-   LINK および \_LINK\_。定義されている場合。  LINK ツールは、処理の前に、環境変数 LINK に定義されているオプションと引数をコマンド ライン引数の先頭に追加し、環境変数\_LINK\_ に定義されているオプションと引数をコマンド ライン引数の末尾に追加します。  
  
-   LIB。定義されている場合。  LINK ツールは、コマンド ラインまたは [\/BASE](../../build/reference/base-base-address.md) オプションで指定したオブジェクト ファイル、ライブラリ ファイル、またはその他のファイルを検索するときに、LIB パスを使用します。  また、オブジェクトで指定された .pdb ファイルを検索するときにも LIB パスを使用します。  LIB 変数では、複数のパスをセミコロンで区切って指定できます。  1 つのパスは Visual C\+\+ インストールの \\lib サブディレクトリを示す必要があります。  
  
-   PATH。ツールが CVTRES を実行する必要があり、LINK 自身と同じディレクトリ内にこのファイルが見つからない場合   \(LINK では、.res ファイルをリンクするために CVTRES を必要とします\)。 PATH は Visual C\+\+ インストールの \\bin サブディレクトリを示す必要があります。  
  
-   TMP。OMF ファイルまたは .res ファイルをリンクするときのディレクトリを指定します。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [コマンド ライン ビルドのパスと環境変数の設定](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)