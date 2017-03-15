---
title: "C ランタイム エラー R6017 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6017
dev_langs:
- C++
helpviewer_keywords:
- R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 903d440dbedbe704ae28be643337619ca1e09c69
ms.lasthandoff: 02/24/2017

---
# <a name="c-runtime-error-r6017"></a>C ランタイム エラー R6017
マルチ スレッド ロックの予期しないエラーです。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリケーションがシャット ダウン内部の問題があるためです。 このエラーのいくつかの理由が考えられますが、これをアプリのコードの欠陥によって発生は、多くの場合。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   使用して、**アプリや機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復またはプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの最新バージョンを確認します。 問題が解決しない場合、アプリケーション ベンダーに問い合わせてください。  
  
 **プログラマのための情報**  
  
 プロセスでは、システム リソースの C ランタイム マルチ スレッドのロックにアクセスしているときに予期しないエラーを受け取りました。 通常、このエラーは、プロセスがランタイム ヒープのデータを誤って変更する場合に発生します。 ただしも発生することによって、ランタイム ライブラリまたはオペレーティング システムのコードで内部エラーです。  
  
 この問題を解決するには、コードのヒープの破損バグを確認します。 詳細と例については、次を参照してください。 [CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)します。 次に、アプリの展開の最新の再頒布可能パッケージを使用していることを確認します。 詳細については、次を参照してください。 [Visual c での配置](../../ide/deployment-in-visual-cpp.md)します。
