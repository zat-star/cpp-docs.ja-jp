---
title: "BSCMAKE コマンドライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c00a3842db37cc5027809f717ac47bd471dd073f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-command-line"></a>BSCMAKE コマンド ライン
BSCMAKE を実行するには、次のコマンドライン構文を使用します。  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 オプションでのみ使用できます、`options`コマンド ラインでフィールドです。  
  
 *Sbrfiles*フィールドは、コンパイラやアセンブラーによって作成された 1 つ以上の .sbr ファイルを指定します。 スペースまたはタブでは、.sbr ファイルの名前を区切ります。 拡張子を指定する必要があります。既定値はありません。 ファイル名は、パスを指定して、オペレーティング システムのワイルドカードを使用することができます (* と?) です。  
  
 インクリメンタル ビルドで、最初のビルドに含まれていない新しい .sbr ファイルを指定できます。 すべてのコントリビューションをブラウザー情報ファイルに保持する場合は、.bsc ファイルの作成に使用された元 (ファイルの切り捨てを含む) すべての .sbr ファイルを指定する必要があります。 .Sbr ファイルを省略すると、ブラウザー情報ファイルにそのファイルの金額が削除されます。  
  
 フル ビルドの切り捨てられた .sbr ファイルを指定しません。 フル ビルドには、すべての指定した .sbr ファイルからの協力が必要です。 フル ビルドを実行する前に、プロジェクトを再コンパイルし、空のファイルで新しい .sbr ファイルを作成します。  
  
 次のコマンドは、3 つの .sbr ファイルから MAIN.bsc という名前のファイルをビルドするを実行します。  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 関連情報については、次を参照してください。 [BSCMAKE コマンド ファイル](../../build/reference/bscmake-command-file-response-file.md)と[BSCMAKE オプション](../../build/reference/bscmake-options.md)です。  
  
## <a name="see-also"></a>参照  
 [BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)