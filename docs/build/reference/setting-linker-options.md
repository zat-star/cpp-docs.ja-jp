---
title: "リンカー オプションの設定 |Microsoft ドキュメント"
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
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ba42921f1e192c90e302b437b9a7d1b4e5eb34e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setting-linker-options"></a>リンカー オプションの設定
内部または外部開発環境、リンカー オプションを設定できます。 各リンカー オプションのトピックでは、開発環境で設定する方法について説明します。 参照してください[リンカー オプション](../../build/reference/linker-options.md)完全な一覧についてはします。  
  
 開発環境の外部リンクを実行する場合は、1 つまたは複数の方法で入力を指定できます。  
  
-   [コマンドライン](../../build/reference/linker-command-line-syntax.md)  
  
-   使用して[コマンド ファイル](../../build/reference/link-command-files.md)  
  
-   [環境変数](../../build/reference/link-environment-variables.md)  
  
 その後にオプションおよびコマンド ファイル、コマンドラインで指定された順序で、環境変数 LINK でリンク最初プロセス オプションを指定します。 オプションは異なる引数を持つで繰り返される場合は、処理された最後の 1 つが優先されます。  
  
 オプションはビルド全体に適用します。特定の入力ファイルに適用することができますオプションはありません。  
  
## <a name="see-also"></a>参照  
 [C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)   
 [リンカー オプション](../../build/reference/linker-options.md)