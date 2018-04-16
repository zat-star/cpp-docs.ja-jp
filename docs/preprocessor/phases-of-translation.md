---
title: "変換フェーズ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- translation phases
- preprocessor, translation
- translation, compiler process
- preprocessor
- file translation [C++], compiler process
- files [C++], translation
ms.assetid: a7f7a8c9-e8ba-4321-9e50-ebfbbdcce9db
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 21cf6efeba83758bed8abe45aba36f025ace16f4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="phases-of-translation"></a>変換フェーズ
C および C++ プログラムは、それぞれがプログラムのテキストの一部を含む 1 つ以上のソース ファイルで構成されます。 ソース ファイルは、インクルード ファイル (`#include` プリプロセッサ ディレクティブを使用して含まれたファイル) と共に、`#if` などの条件付きコンパイル ディレクティブによって削除されたコードのセクションを除き、"翻訳単位" と呼ばれます。  
  
 ソース ファイルは、さまざまなタイミングで変換できます。期限切れのファイルのみを変換する場合、これが一般的です。 変換された翻訳単位は個別のオブジェクト ファイルまたはオブジェクト コード ライブラリに処理できます。 次に、変換された各翻訳単位は、実行可能プログラムやダイナミック リンク ライブラリ (DLL) を形成するためにリンクされます。  リンカー入力として使用できるファイルの詳細については、次を参照してください。 [LINK の入力ファイル](../build/reference/link-input-files.md)です。  
  
 翻訳単位は次を使用して通信できます。  
  
-   外部リンケージを持つ関数の呼び出し。  
  
-   外部リンケージを持つクラス メンバー関数の呼び出し。  
  
-   外部リンケージを持つオブジェクトの直接的な変更。  
  
-   ファイルの直接的な変更。  
  
-   プロセス間通信 (Microsoft Windows ベースのアプリケーションのみ)。  
  
 次の一覧では、コンパイラがファイルを変換するフェーズについて説明します。  
  
 *文字のマッピング*  
 ソース ファイルの文字はソースの内部表現にマップされます。 トライグラフ シーケンスはこのフェーズの単一文字の内部表現に変換されます。  
  
 *行スプライス*  
 バック スラッシュで終わるすべての行 (**\\**) の直後に、改行を配置して、文字が、物理行から論理行を形成するソース ファイルの次の行と結合されます。 これが空でない場合、ソース ファイルは前に円記号が付いていない改行文字で終了する必要があります。  
  
 トークン化  
 ソース ファイルはプリプロセッサ トークンと空白文字に分割されます。 ソース ファイル内のコメントは、それぞれ 1 個の空白文字と置き換えられます。 改行文字は保持されます。  
  
 *前処理*  
 前処理ディレクティブが実行され、マクロがソース ファイルに展開されます。 `#include` ステートメントは、インクルードされたテキストで前の 3 つの書き換え手順から開始する変換を呼び出します。  
  
 *文字セットのマップ*  
 すべてのソース文字セット メンバーとエスケープ シーケンスは、実行文字セットの同等のものに変換されます。 Microsoft C および C++ にとって、ソース文字セットと実行文字セットはいずれも ASCII 文字セットです。  
  
 *文字列の連結*  
 すべての隣接する文字列とワイド文字列リテラルは連結されます。 たとえば、`"String " "concatenation"` が `"String concatenation"` になります。  
  
 *翻訳*  
 すべてのトークンは、構文的および意味的に分析され、オブジェクト コードに変換されます。  
  
 *リンケージ*  
 すべての外部参照は実行可能プログラムまたはダイナミック リンク ライブラリを作成するために解決されます。  
  
 コンパイラは、構文エラーを検出した変換のフェーズ中に警告やエラーを発行します。  
  
 リンカーは、すべての外部参照を解決し、1 つ以上の個別に処理された翻訳単位を結合して、標準ライブラリと共に実行可能プログラムまたは DLL を作成します。  
  
## <a name="see-also"></a>参照  
 [プリプロセッサ](../preprocessor/preprocessor.md)