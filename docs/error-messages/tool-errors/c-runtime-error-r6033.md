---
title: "C ランタイム エラー R6033 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6033
dev_langs:
- C++
helpviewer_keywords:
- R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
caps.latest.revision: 4
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 27bf1610d6db9f778a4355183257fb237fc4a175
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="c-runtime-error-r6033"></a>C ランタイム エラー R6033
ネイティブ コードの初期化中にこのアセンブリの MSIL コードを使用しようとしてください。 これは、アプリケーションにバグを示します。 MSIL でコンパイルを呼び出すときの結果になる可能性があります (/clr) ネイティブのコンス トラクターからまたは Dll からエクスポートされた関数。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリケーションがシャット ダウン内部の問題があるためです。 このエラーは、アプリケーションで、バグ、またはアドインまたは拡張を使用して、バグによって可能性があります。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   使用して、**アプリや機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復またはプログラムを再インストールします。  
> -   使用して、**アプリや機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を削除、修復の拡張またはアドインを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの最新バージョンを確認します。 問題が解決しない場合、アプリケーション ベンダーに問い合わせてください。  
  
 **プログラマのための情報**  
  
 この診断は、ローダー ロック中に MSIL 命令が実行されたことを示します。 これは、ネイティブ C++/clr フラグを使用してコンパイルした場合に発生します。 マネージ コードが含まれるモジュールからのみ/clr フラグを使用してください。 詳細については、次を参照してください。[混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)します。
