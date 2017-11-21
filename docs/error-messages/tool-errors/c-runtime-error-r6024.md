---
title: "C ランタイム エラー R6024 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6024
dev_langs: C++
helpviewer_keywords: R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2d032bbcb6e28d78f5e43b9c12499c6d47ca0310
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6024"></a>C ランタイム エラー R6024
_onexit/atexit テーブル領域が足りません。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン、内部メモリの問題があるためです。 このエラーは通常、非常に低いメモリ条件では、またはまれには、プログラムのバグまたはによって使用されている Visual C ライブラリの破損に発生します。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   その他の実行中のアプリケーションを閉じるか、メモリを解放する、コンピューターを再起動します。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復またはプログラムを再インストールします。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復または、Microsoft Visual C 再頒布可能のすべてのコピーを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 使用可能なメモリがないために、このエラーが発生した、`_onexit`または`atexit`関数。 このエラーは、メモリ不足の状況で発生します。 ユーザー データの保存とクリーン アプリの実行を支援するアプリの起動時に割り当て済みのバッファーがメモリの少ない状況で終了を検討する可能性があります。