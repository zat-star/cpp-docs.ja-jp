---
title: "C ランタイム エラー R6017 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6017
dev_langs:
- C++
helpviewer_keywords:
- R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57345feed2044683a1d5fd2a6ee7d14c412a827d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6017"></a>C ランタイム エラー R6017
予期しないマルチ スレッドのロック エラーです。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 このエラーは、いくつかの理由が考えられますが、これをアプリのコードの欠陥によって発生は多くの場合。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復またはプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの** ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 プロセスは、システム リソースの C ランタイム マルチ スレッドのロックにアクセスしようとしています。 中に予期しないエラーを受け取りました。 このエラーは、通常、プロセスは、ランタイム ヒープ データを誤って変更する場合に発生します。 ただし、これことができますも発生することによって、ランタイム ライブラリまたはオペレーティング システムのコードの内部エラー。  
  
 この問題を解決するには、コード内のヒープ破損のバグを確認します。 詳細と例については、次を参照してください。 [CRT デバッグ ヒープの詳細](/visualstudio/debugger/crt-debug-heap-details)です。 次に、アプリの展開に関する最新の再頒布可能パッケージを使用していることを確認します。 詳細については、次を参照してください。 [Visual c での展開](../../ide/deployment-in-visual-cpp.md)です。