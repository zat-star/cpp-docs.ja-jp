---
title: "C ランタイム エラー R6019 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6019
dev_langs:
- C++
helpviewer_keywords:
- R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4ab7054bdce76aa1dd0b443993cfac8eeb8ecc7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="c-runtime-error-r6019"></a>C ランタイム エラー R6019
コンソール デバイスを開けません。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン、コンソールにアクセスしようとしましたが、十分なアクセス許可がないためです。 このエラーは、いくつかの理由が考えられますが、通常は、管理者は、プログラムを実行する必要がありますか、プログラムでバグがあるためです。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   管理者としてプログラムを実行します。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復またはプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの** ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 このエラーは、アプリにコンソール関数が呼び出されますが、オペレーティング システムでは、コンソールへのアクセスを付与しなかったために発生します。 除くデバッグ モードでコンソールの機能は一般に許可されていません Microsoft ストア アプリでします。 アプリを実行する管理者特権を必要とする場合は、既定では管理者として実行するインストールを確認します。