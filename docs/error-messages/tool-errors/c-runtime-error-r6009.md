---
title: "C ランタイム エラー R6009 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6009
dev_langs: C++
helpviewer_keywords: R6009
ms.assetid: edfb1f8b-3807-48f4-a994-318923b747ae
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 137bb74bcc091721633fe22fc9c56ef6ce99a535
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6009"></a>C ランタイム エラー R6009
環境に必要な領域が足りません。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン、内部メモリの問題があるためです。 このエラーは、いくつかの理由が考えられますが、多くの場合、これがによる、非常に低いメモリの状態、環境変数、またはプログラムのバグによって取得されるメモリが多すぎます。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   その他の実行中のアプリケーションを閉じるか、メモリを解放する、コンピューターを再起動します。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復またはプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの** ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 プログラムを読み込むための十分なメモリが十分なメモリを作成する、 **envp**配列。  これは、非常に低いメモリ条件、または非常に大規模な環境変数を使用して可能性があります。 次の解決策のいずれかを検討してください。  
  
-   プログラムに使用可能なメモリの量を増やします。  
  
-   コマンドライン引数のサイズと数を削減します。  
  
-   不要な変数を削除することで環境のサイズを削減します。