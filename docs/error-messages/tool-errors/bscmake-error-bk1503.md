---
title: "BSCMAKE エラー BK1503 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1503
dev_langs: C++
helpviewer_keywords: BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86f2b6d282857409cdb1e1d49e04775e9886cde4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE エラー BK1503
'filename' をファイルに書き込みできません [: 理由]  
  
 BSCMAKE では、ブラウザーの 1 つのデータベースへのコンパイル中に生成された .sbr ファイルを結合します。 結果として得られるブラウザー データベースは、64 MB を超えた場合、または入力 (.sbr) ファイルの数が 4092 個を超えた場合は、このエラーが出力されます。  
  
 問題の原因が 4092 以上の .sbr ファイルである場合は、入力ファイルの数を減らす必要があります。 Visual Studio 内でこれには、によって[/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) 、プロジェクト全体、ファイルをファイルごとに再チェックします。  
  
 問題の原因が、64 MB より大きい .bsc ファイルである場合は、入力としての .sbr ファイルの数を減らすと、生成された .bsc ファイルのサイズが低下します。 さらに、/Em (マクロ展開シンボルを除外する)、/El (ローカル変数の除外)、および/Es (システム ファイルを除外する) を使用してブラウザー情報の量を削減する可能性があります。  
  
## <a name="see-also"></a>参照  
 [BSCMAKE オプション](../../build/reference/bscmake-options.md)