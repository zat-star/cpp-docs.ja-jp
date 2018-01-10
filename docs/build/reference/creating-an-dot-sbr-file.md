---
title: "作成します。Sbr ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d87b71daaf5d7b37e67c2c0e56e844bd5251a490
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-sbr-file"></a>.sbr ファイルの作成
BSCMAKE の入力ファイルは、.sbr ファイルです。 コンパイラでは、コンパイルされる各オブジェクト ファイル (.obj) の .sbr ファイルを作成します。 ビルドまたはブラウザー情報ファイルを更新すると、プロジェクトのすべての .sbr ファイルがディスクで使用できる場合があります。  
  
 すべての可能な情報を含む .sbr ファイルを作成するには、指定[/FR](../../build/reference/fr-fr-create-dot-sbr-file.md)です。  
  
 ローカル シンボルを含まない .sbr ファイルを作成するには指定[/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)です。 .Sbr ファイルにローカル シンボルが含まれている場合も省略できますそれら .bsc ファイルから BSCMAKE を使用して、 [/El オプション](../../build/reference/bscmake-options.md)`.`  
  
 完全なコンパイルを実行せず、.sbr ファイルを作成できます。 たとえば、オプションを指定できます、/Zs 構文チェックを実行し、/FR または/fr を指定する場合も、.sbr ファイルを作成するようコンパイラにする  
  
 ビルド プロセスは、.sbr ファイルをパック未参照の定義を削除する場合より効率的にできます。 コンパイラは、自動的に .sbr ファイルをパックします。  
  
## <a name="see-also"></a>参照  
 [.bsc ファイルのビルド](../../build/reference/building-a-dot-bsc-file.md)