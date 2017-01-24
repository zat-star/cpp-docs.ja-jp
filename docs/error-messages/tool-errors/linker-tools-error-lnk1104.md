---
title: "リンカ ツール エラー LNK1104 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1104"
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイル 'filename' を開けません。  
  
 ツールは、指定されたファイルを開くことができませんでした。  
  
 次のような原因をチェックして問題を解決するには:  
  
-   ディスク領域が十分ではありません。  
  
-   ファイルが存在しません。  
  
-   プロジェクトのプロパティ ページのダイアログ ボックスでライブラリを指定するとき、ライブラリ名をスペース \(コンマではない\) で区切る必要があります。  
  
-   ファイル名またはパスが正しくありません。  
  
-   ドライブの指定が無効です。  
  
-   ファイルのアクセス許可が不十分です  
  
-   `filename` のパスが 260 文字を超えています。  
  
-   指定されたファイルの名前が `LNKn` \(一時ファイルのリンカーによって生成されるファイル名\) である場合、TMP 環境変数に指定されたディレクトリが存在しない可能性があります。または、複数のディレクトリが TMP 環境変数に指定されている可能性があります。 \(TMP 環境変数に指定できるディレクトリのパスは 1 つだけです。\)  
  
-   ライブラリ名でエラー メッセージが発生し、以前の Microsoft Visual C\+\+ 開発システムから最近.mak ファイルを移植した場合、ライブラリは無効になることがあります。 ライブラリがこの環境でまだ存在することを確認してください。  
  
-   別のプログラムのファイルが開かれている可能性があり、リンカーはそのファイルに書き込めません。  
  
-   LIB 環境変数が正しくありません。 LIB 環境変数を更新する方法については、[\[VC\+\+ ディレクトリ\] プロパティ ページ](../Topic/VC++%20Directories%20Property%20Page.md) を参照してください。 必要なライブラリが格納されるディレクトリがここに一覧表示されていることを確認します。  
  
 リンカーが一時ファイルを使用するケースはいくつかあります。 十分なディスク スペースがある場合でも、リンクが非常に大きいと、アドレス スペースを消費または断片化する可能性があります。  
  
 修復の可能性がある解決策  
  
-   [\/OPT \(最適化\)](../../build/reference/opt-optimizations.md) を使用する。中間 COMDAT 除去を行うと、すべてのオブジェクト ファイルが複数回読み取られます。  
  
-   Windows XP にアップグレードする。