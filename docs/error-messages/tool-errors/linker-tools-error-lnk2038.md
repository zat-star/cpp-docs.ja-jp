---
title: "リンカ ツール エラー LNK2038 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2038"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2038"
ms.assetid: b8d0fb35-eee6-4f52-b3c4-239cb4f65656
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# リンカ ツール エラー LNK2038
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\<name\>' の不一致が検出されました。値 '\<value 1\>' が \<filename.obj\> の値 '\<value 2\>' と一致しません。  
  
 シンボルの不一致がリンカーによって検出されました。  このエラーは、アプリの各部分 \(アプリがリンクするライブラリやその他のオブジェクト コードを含む\) が、競合するシンボル定義を使用していることを示しています。  [detect mismatch](../../preprocessor/detect-mismatch.md) プラグマは、このようなシンボルを定義し、競合する値を検出するために使用されます。  
  
### このエラーを解決するには  
  
-   このエラーは、プロジェクトのオブジェクト ファイルが古い形式のときに発生する可能性があります。  このエラーに対して他のソリューションを実行する前に、オブジェクト ファイルが最新であることを検証するために、クリーン ビルドを実行してください。  
  
-   Visual Studio は、実行時エラーまたはその他の予測できない動作を発生させる可能性のある互換性のないコードのリンクを防ぐために、次のシンボルを定義します。  
  
     `_MSC_VER`  
     アプリまたはライブラリのビルドに使用される Visual C\+\+ コンパイラのメジャー バージョン番号とマイナー バージョン番号を示します。  Visual C\+\+ コンパイラの 1 種類のバージョンを使用してコンパイルされたコードは、さまざまなメジャー バージョン番号とマイナー バージョン番号のあるバージョンを使用してコンパイルされたコードと互換性がありません。  詳細については、「[定義済みマクロ](../../preprocessor/predefined-macros.md)」の「`_MSC_VER`」を参照してください。  
  
     使用している Visual C\+\+ コンパイラのバージョンと互換性のないライブラリとリンクしている場合、および、互換性のあるバージョンのライブラリを取得またはビルドできない場合は、以前のバージョンのコンパイラを使用して、プロジェクトの **\[プラットフォーム ツールセット\]** のプロパティを変更するだけで、プロジェクトをビルドできます。  詳細については、「[方法: ターゲット フレームワークおよびプラットフォームのツールセットを変更する](../../build/how-to-modify-the-target-framework-and-platform-toolset.md)」を参照してください。  
  
     `_ITERATOR_DEBUG_LEVEL`  
     C\+\+ 標準ライブラリで有効になっているセキュリティ機能とデバッグ機能のレベルを示します。  これらの機能は、特定の C\+\+ 標準ライブラリのオブジェクトの表示を変更できるため、こうしたオブジェクトは、異なるセキュリティ機能とデバッグ機能を使用するオブジェクトと互換性がなくなります。  詳細については、「[\_ITERATOR\_DEBUG\_LEVEL](../../standard-library/iterator-debug-level.md)」を参照してください。  
  
     `RuntimeLibrary`  
     アプリまたはライブラリで使用する C\+\+ 標準ライブラリおよび C ランタイムのバージョンを示します。  C\+\+ 標準ライブラリまたは C ランタイムの 1 種類のバージョンを使用するコードは、異なるバージョンを使用するコードと互換性がありません。  詳細については、「[\/MD、\/MT、\/LD \(ランタイム ライブラリの使用\)](../../build/reference/md-mt-ld-use-run-time-library.md)」を参照してください。  
  
     `_PPLTASKS_WITH_WINRT`  
     [並列パターン ライブラリ \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md) を使用するコードが、[\/ZW](../../build/reference/zw-windows-runtime-compilation.md) コンパイラ オプションに異なる設定を使用してコンパイルしたオブジェクトにリンクされています \(**\/ZW** は C\+\+\/CX をサポート\)。PPL を使用するか PPL に依存するコードのコンパイルでは、**\/ZW** にアプリの残りの部分と同じ設定を使用する必要があります。  
  
     これらのシンボルの値が、Visual Studio ソリューションのプロジェクト全体で一貫していることと、使用中のアプリがリンクしているコードとライブラリに一致していることを確認してください。  
  
## 参照  
 [リンカー ツール エラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)