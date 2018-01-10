---
title: "C ランタイム エラー R6033 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6033
dev_langs: C++
helpviewer_keywords: R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f2ef73d3cb82a65c8114d2e7f921b47ffd45d65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6033"></a>C ランタイム エラー r6033 が発生
ネイティブ コードの初期化中にこのアセンブリから MSIL コードを使用しようとしてください。 これは、アプリケーションでバグを示します。 MSIL でコンパイルの呼び出しの結果である可能性があります (/clr) 関数は、ネイティブのコンス トラクターから、または Dll からエクスポートします。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 このエラーは、アプリのバグまたはアドインまたは使用されている拡張機能でバグ可能性があります。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復またはプログラムを再インストールします。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**削除、修復、または任意の拡張機能またはアドインを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの** ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 この診断では、ローダー ロック中に MSIL 命令が実行されたことを示します。 これは、/clr フラグを使用してネイティブ C++ をコンパイルした場合に発生します。 のみを含むマネージ コード モジュールで/clr フラグを使用します。 詳細については、次を参照してください。[混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)です。