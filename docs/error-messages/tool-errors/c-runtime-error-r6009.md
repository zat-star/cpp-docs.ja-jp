---
title: "C ランタイム エラー R6009 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6009
dev_langs:
- C++
helpviewer_keywords:
- R6009
ms.assetid: edfb1f8b-3807-48f4-a994-318923b747ae
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f0a5401b32b5bd2918b316a8dd1b16ec3db1e8f3
ms.lasthandoff: 02/24/2017

---
# <a name="c-runtime-error-r6009"></a>C ランタイム エラー R6009
環境に必要な領域が足りません。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリケーションがシャット ダウン、内部メモリの問題があるためです。 このエラーのいくつかの理由が考えられますが、通常、非常に低いメモリの状態、大量のメモリが環境変数、またはプログラムのバグが実行すると発生が。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   その他の実行中のアプリケーションを閉じるか、メモリを解放する、コンピューターを再起動します。  
> -   使用して、**アプリや機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復またはプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの最新バージョンを確認します。 問題が解決しない場合、アプリケーション ベンダーに問い合わせてください。  
  
 **プログラマのための情報**  
  
 できました、プログラムを読み込むための十分なメモリが十分なメモリを作成する、 **envp**配列。  これは、非常に低いメモリ条件、または非常に大規模な環境変数の使用法可能性があります。 次の解決策のいずれかを検討してください。  
  
-   プログラムに使用可能なメモリを増やします。  
  
-   コマンドライン引数のサイズと数を削減します。  
  
-   環境のサイズを小さくには、不要な変数を削除します。
