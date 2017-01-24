---
title: "コマンド ラインの警告 D9025 | Microsoft Docs"
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
  - "D9025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9025"
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コマンド ラインの警告 D9025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'option1' が 'option2' によってオーバーライドされました。  
  
 オプション *option1* が指定されましたが、オプション *option2* によってオーバーライドされました。  したがって、オプション *option2* が使用されます。  
  
 2 つのオプションで互いに矛盾したり互換性のないディレクティブが指定されている場合、コマンド ラインの最も右側のオプションで指定されているディレクティブが使用されます。  
  
 開発環境でのコンパイル時にこの警告が発生し、矛盾するオプションの場所が不明な場合は、次のことを検討します。  
  
-   オプションは、コードまたはプロジェクトのプロジェクト設定で指定できます。  コンパイラの [&#91;コマンド ライン&#93; プロパティ ページ](../../ide/command-line-property-pages.md)を確認し、\[すべてのオプション\] フィールドに矛盾するオプションが見つかった場合は、オプションはプロジェクトのプロパティ ページで設定されています。それ以外の場合は、オプションはソース コードで設定されています。  
  
     オプションがプロジェクトのプロパティ ページで設定されている場合は、ソリューション エクスプローラーでプロジェクト ノードが選択されている状態で、コンパイラの \[プリプロセッサ\] プロパティ ページを確認します。ここでオプションが設定されていない場合は、ソリューション エクスプローラーでソース コード ファイルごとに \[プリプロセッサ\] プロパティ ページを調べて、オプションが追加されていないことを確認します。  
  
     オプションがコードで設定されている場合は、コード内または Windows のヘッダー内に設定されています。プリプロセス済みファイルを作成して \([\/P](../../build/reference/p-preprocess-to-a-file.md)\)、それをシンボルで検索してみます。