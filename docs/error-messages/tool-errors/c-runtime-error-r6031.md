---
title: "C ランタイム エラー R6031 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6031
dev_langs:
- C++
helpviewer_keywords:
- R6031
ms.assetid: 805d4cd1-cb2f-43fe-87e6-e7bd5b7329c5
caps.latest.revision: 5
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
ms.openlocfilehash: d32c46d254963675cc283a8934a6a7b089e745ca
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="c-runtime-error-r6031"></a>C ランタイム エラー R6031
CRT を複数回初期化しようとしてください。 これは、アプリケーションにバグを示します。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリケーションがシャット ダウン内部の問題があるためです。 これがまたは発生するバグ アプリケーションで、アドオンまたはアプリケーションを使用して拡張機能でバグです。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   使用して、**アプリや機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復またはプログラムを再インストールします。  
> -   使用して、**アプリや機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を削除するには、修復またはアプリケーションで使用されるアドオンまたは拡張機能のプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。  
> -   アプリの最新バージョンを確認します。 問題が解決しない場合、アプリケーション ベンダーに問い合わせてください。  
  
 **プログラマのための情報**  
  
 この診断は、ローダー ロック中に MSIL 命令が実行されたことを示します。 詳細については、次を参照してください。[混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)します。
