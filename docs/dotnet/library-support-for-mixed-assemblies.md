---
title: "混在アセンブリのためのライブラリ サポート | Microsoft Docs"
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
  - "ライブラリ [C++], 混在アセンブリ"
  - "混在アセンブリ [C++], ライブラリのサポート"
  - "msvcm90[d].dll"
  - "msvcmrt[d].lib"
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 混在アセンブリのためのライブラリ サポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ では、[\/clr \(共通言語ランタイムのコンパイル\)](../build/reference/clr-common-language-runtime-compilation.md) でコンパイルされたアプリケーションに対する標準 C\+\+ ライブラリ、共通ランタイム ライブラリ \(CRT\)、ATL、および MFC の使用がサポートされています。  これにより、これらのライブラリを使用する既存のアプリケーションでも、同じように .NET Framework 機能を使用できます。  
  
 このサポートには、次の新しい DLL ライブラリおよびインポート ライブラリが導入されています。  
  
-   \/clr でコンパイルする場合は Msvcmrt\[d\].lib。  混在アセンブリは、このインポート ライブラリにリンクします。  
  
-   \/clr:pure でコンパイルする場合は Msvcm90\[d\].dll および Msvcurt\[d\].lib。  DLL は、マネージ C ランタイム \(CRT\) をサポートする混在アセンブリであり、グローバル アセンブリ キャッシュ \(GAC: Global Assembly Cache\) にインストールされたマネージ アセンブリに含まれています。  純粋なアセンブリは、このインポート ライブラリにリンクし、最終的に Msvcm90.dll. にバインドされます。  
  
 このサポートには、関連する利点がいくつかあります。  
  
-   CRT および標準 C\+\+ ライブラリは、混在するコードと純粋なコードの両方に使用できます。  用意されている CRT および標準 C\+\+ ライブラリは確認可能ではありません。そのため、最終的には、呼び出しが、ネイティブ コードから使用するのと同じ CRT および標準 C\+\+ ライブラリにルーティングされます。  
  
-   純粋なイメージおよび混在したイメージで統合された例外処理を修正します。  
  
-   純粋なイメージおよび混在したイメージにおける C\+\+ 変数の静的な初期化を行います。  
  
-   マネージ コードの per\-AppDomain 変数および per\-process 変数をサポートします。  
  
-   Visual C\+\+ .NET および Visual C\+\+ .NET 2003 の複合 DLL に適用されたローダー ロックの問題を解決します。  
  
 さらに、このサポートには、次の制限事項があります。  
  
-   CRT DLL モデルのみがサポートされます \(\/clr または \/clr:pure でコンパイルされたコードの場合\)。  
  
-   純粋なオブジェクトと複合オブジェクトで Visual C\+\+ ライブラリを使用する場合、1 つのイメージにこれらのオブジェクトを混在させることはできません \(純粋なイメージ内では、すべてのオブジェクトが純粋である必要があります\)。  これらのオブジェクトを混在させると、リンク時のエラーが発生します。  
  
 共通言語ランタイム \(CLR: Common Language Runtime\) は、旧バージョンで動作することが保証されていないため、現在のバージョンに更新する必要があります。  このような変更によって作成されたコードは、CLR Version 1.x では実行されません。  
  
## 参照  
 [混在 \(ネイティブおよびマネージ\) アセンブリ](../Topic/Mixed%20\(Native%20and%20Managed\)%20Assemblies.md)