---
title: "C ランタイム エラー R6026 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6026
dev_langs:
- C++
helpviewer_keywords:
- R6026
ms.assetid: 7ea751f8-fc20-46ab-99ef-84c95ca0b6b4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a0baa9806476534bd877f8177d20bbe9da80d3da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6026"></a>C ランタイム エラー R6026
stdio 初期化領域が足りません。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン、内部メモリの問題があるためです。 このエラーは、いくつかの理由が考えられますが、非常に低いメモリ条件によってはこれが起こります。 また、アプリのバグ、使用して、Visual C ライブラリの破損またはドライバーによっても発生ことができます。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   その他の実行中のアプリケーションを閉じるか、メモリを解放する、コンピューターを再起動します。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復またはプログラムを再インストールします。  
> -   使用して、アプリが他のアプリまたはドライバーの最新のインストール前に動作していた場合、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を削除する、新しいアプリケーションまたはドライバー、およびアプリをもう一度やり直してください。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復または、Microsoft Visual C 再頒布可能のすべてのコピーを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの** ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 このエラーは、標準的な I/O サポート、C ランタイムでの初期化に使用できる十分な空きメモリ容量がない場合に発生します。 このエラーは、通常、アプリの起動時に発生します。 アプリおよびドライバーと dll が読み込まれますが起動時に、ヒープを破損しないことを確認します。