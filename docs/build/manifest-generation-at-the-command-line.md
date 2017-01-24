---
title: "コマンド ラインでのマニフェスト生成 | Microsoft Docs"
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
  - "マニフェスト ツール (mt.exe)"
  - "マニフェスト [C++]"
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コマンド ラインでのマニフェスト生成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

nmake または同様のツールを使用してコマンド ラインから C\/C\+\+ アプリケーションをビルドすると、マニフェストは、リンカーがすべてのオブジェクト ファイルを処理し、最終的なバイナリをビルドした後に生成されます。  リンカーは、オブジェクト ファイルに格納されたアセンブリ情報を収集し、この情報を最終的なマニフェスト ファイルに結合します。  既定ではリンカー binary\_name.extension.manifest という名前の最終的 \<なバイナリを記述\<する\>ファイルを\>生成します。  リンカーは、マニフェスト ファイルをバイナリに埋め込みません。外部ファイルとしてのマニフェストの生成だけができます。  マニフェストを最終的なバイナリに埋め込むには、[マニフェスト ツール \(mt.exe\)](http://msdn.microsoft.com/library/aa375649) を使用したり、マニフェストをリソース ファイルにコンパイルしたりするなどいくつかの方法があります。  マニフェストを最終的なバイナリに埋め込んでインクリメンタル リンク、署名、エディット コンティニュなどの機能を有効にする場合は、固有の規則に従う必要があることに注意してください。  コマンド ラインでビルドする場合のこれらのオプションおよびその他のオプションについては、「[方法 : マニフェストを C\/C\+\+ アプリケーションに埋め込む](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)」を参照してください。  
  
## 参照  
 [\[マニフェスト\]](http://msdn.microsoft.com/library/aa375365)   
 [\/INCREMENTAL \(インクリメンタル リンクを行う\)](../build/reference/incremental-link-incrementally.md)   
 [厳密名アセンブリ \(アセンブリ署名\)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)   
 [エディット コンティニュ](../Topic/Edit%20and%20Continue.md)   
 [C\/C\+\+ プログラムのマニフェスト生成についての理解](../Topic/Understanding%20Manifest%20Generation%20for%20C-C++%20Programs.md)