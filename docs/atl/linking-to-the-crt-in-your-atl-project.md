---
title: "ATL プロジェクトでの CRT へのリンク | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DllMainCRTStartup"
  - "wWinMainCRTStartup"
  - "WinMainCRTStartup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, C ランタイム ライブラリ (CRT)"
  - "CRT, リンク (ATL と)"
  - "DllMainCRTStartup メソッド"
  - "WinMainCRTStartup メソッド"
  - "wWinMainCRTStartup メソッド"
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ATL プロジェクトでの CRT へのリンク
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[C ランタイム ライブラリ](../c-runtime-library/crt-library-features.md) \(CRT: C Run\-Time Library\) には、ATL 開発におけるプログラミングを大幅に簡略化できる関数が多数用意されています。  ATL プロジェクトはすべて CRT ライブラリにリンクされます。  メソッドのリンクの長所と短所については、「[CRT へのリンクで使用されるメソッドの利点とトレードオフ](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md)」を参照してください。  
  
## CRT とのリンクによるプログラム イメージへの影響  
 CRT に静的にリンクする場合は、CRT のコードを実行可能イメージに挿入します。イメージを実行するシステム上に CRT DLL は必要ありません。  CRT に動的にリンクする場合は、CRT DLL 内のコードそのものではなく、そのコードへの参照をイメージに挿入します。  イメージを特定のシステムで実行するには、そのシステム上に CRT DLL が必要です。  CRT に動的にリンクする場合でも、**DllMainCRTStartup** などの一部のコードが静的にリンクされる場合があります。  
  
 イメージをリンクする場合は、オペレーティング システムがそのイメージを読み込んだ後で、呼び出しを開始するエントリ ポイントを明示的または暗黙的に指定します。  DLL の場合、既定のエントリ ポイントは **DllMainCRTStartup** です。  EXE の場合、既定のエントリ ポイントは **WinMainCRTStartup** です。  既定のエントリ ポイントは、\/ENTRY リンカー オプションでオーバーライドできます。  CRT は、**DllMainCRTStartup**、**WinMainCRTStartup**、および **wWinMainCRTStartup** \(EXE の Unicode エントリ ポイント\) の実装を提供します。  CRT が提供するこれらのエントリ ポイントは、グローバル オブジェクトのコンストラクターを呼び出し、一部の CRT 関数で使用される別のデータ構造体を初期化します。  静的にリンクする場合は、スタートアップ コードの追加によってイメージ サイズは約 25 KB 分増えます。  動的にリンクした場合は、コードの大部分が DLL 内にあるため、イメージのサイズを小さく抑えることができます。  
  
 詳細については、リンカーに関する「[\/ENTRY \(エントリ ポイント シンボル\)](../build/reference/entry-entry-point-symbol.md)」というトピックを参照してください。  
  
## 最適化オプション  
 リンカー オプション \/OPT:NOWIN98 を使用すると、Windows 98 システムでの読み込み時間は長くなりますが、既定の ATL コントロールのサイズを 10 KB 縮小できます。  リンク オプションの詳細については、｢[\/OPT \(最適化\)](../build/reference/opt-optimizations.md)｣を参照してください。  
  
## 参照  
 [ATL および C ランタイム コードによるプログラミング](../atl/programming-with-atl-and-c-run-time-code.md)   
 [ランタイム ライブラリの動作](../build/run-time-library-behavior.md)