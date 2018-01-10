---
title: "コマンドラインの警告 D9025 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9025
dev_langs: C++
helpviewer_keywords: D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d95c4c16b472f0e1b37a981df7f73ff573d06447
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9025"></a>コマンド ラインの警告 D9025
・ オプション '2' と ' オプション 1' をオーバーライドします。  
  
 *Option1*オプションが指定されましたが、によってオーバーライドされたし*・ オプション 2*です。 *・ オプション 2*オプションが使用されました。  
  
 2 つのオプションは、矛盾するまたは互換性のないディレクティブを指定する場合は、ディレクティブを指定または黙示にかかわらず、コマンドラインで一番右側にあるオプションが使用されます。  
  
 開発環境からコンパイルするときに、この警告を取得していないことを確認して、競合するオプションがから送信されて、次を考慮してください。  
  
-   コード内、またはプロジェクトのプロジェクト設定で、オプションを指定できます。 コンパイラを見る場合[コマンド ライン プロパティ ページ](../../ide/command-line-property-pages.md)で競合するオプションを表示する場合と、**すべてのオプション**オプションは、プロジェクトのプロパティ ページで、それ以外の場合のオプションを設定し、フィールドソース コードで設定されます。  
  
     オプションがプロジェクトのプロパティ ページで設定されている場合は、(ソリューション エクスプ ローラーでプロジェクト ノード) のコンパイラのプリプロセッサのプロパティ ページで確認します。  設定がある、設定を確認してプリプロセッサ プロパティ ページ内の各ソース コード ファイル (ソリューション エクスプ ローラー) を確認するオプションが表示されない場合に追加されませんがあります。  
  
     コード内のオプションが設定されている場合は、コード内、または windows のヘッダーで設定でした。  プリプロセス済みのファイルを作成しようとする可能性があります ([/P](../../build/reference/p-preprocess-to-a-file.md)) シンボルを検索します。