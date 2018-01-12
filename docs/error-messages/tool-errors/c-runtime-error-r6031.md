---
title: "C ランタイム エラー R6031 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6031
dev_langs: C++
helpviewer_keywords: R6031
ms.assetid: 805d4cd1-cb2f-43fe-87e6-e7bd5b7329c5
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 260c316ad43ce39a60cb7e54137a363754c1ddf7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6031"></a>C ランタイム エラー R6031
CRT を複数回初期化しようとしてください。 これは、アプリケーションでバグを示します。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 これは、可能性がありますまたは発生するバグ、アプリのバグ アドオンや、アプリが使用する拡張機能です。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復またはプログラムを再インストールします。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を削除するには、修復またはアプリで使用されるアドオンまたは拡張機能のプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの** ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 この診断では、ローダー ロック中に MSIL 命令が実行されたことを示します。 詳細については、次を参照してください。[混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)です。