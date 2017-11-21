---
title: "3. ランタイム ライブラリ関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f693c3ff8bc3e44d47f885b6fb4c0d09b36fdbde
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="3-run-time-library-functions"></a>3.ランタイム ライブラリ関数
このセクションでは、OpenMP C および C++ ランタイム ライブラリ関数について説明します。 ヘッダー  **\<omp.h >** 2 つの型が、制御およびクエリを並列実行環境とロック データへのアクセスを同期するために使用できる関数を使用できるいくつかの関数を宣言します。  
  
 型**omp_lock_t**オブジェクトの種類は、ロックが使用できる、ことを表現すること、またはスレッドがロックを所有しています。 これらのロックをいいます*単純ロック*です。  
  
 型**omp_nest_lock_t**はオブジェクトの種類を表すいずれかの可能なロックを使用、またはロックを所有するスレッドの両方の id と*入れ子カウント*(下記参照)。 これらのロックをいいます*入れ子にできるロック*です。  
  
 ライブラリ関数は、"C"リンケージを持つ外部関数です。  
  
 この章の説明は、次のトピックに分かれています。  
  
-   実行環境関数 (を参照してください[セクション 3.1](../../parallel/openmp/3-1-execution-environment-functions.md)ページ 35)。  
  
-   ロック関数 (を参照してください[セクション 3.2](../../parallel/openmp/3-2-lock-functions.md) 41 ページ上)。