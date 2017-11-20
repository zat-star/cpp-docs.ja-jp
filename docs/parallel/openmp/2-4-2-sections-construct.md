---
title: "2.4.2 sections のコンストラクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 22aa4cc1bde59234d70803c2e878d3fbf83f499e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="242-sections-construct"></a>2.4.2 sections のコンストラクト
**セクション**ディレクティブを識別、noniterative work-sharing コンス トラクターの構造体をチーム内のスレッドに分割するにはセットを指定します。 各セクションでは、チーム内のスレッドで 1 回実行されます。 構文、**セクション**ディレクティブは、次のようにします。  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block ]  
...  
}  
```  
  
 句では、次のいずれかです。  
  
 **プライベート (** *変数一覧* **)**  
  
 **firstprivate (** *変数一覧* **)**  
  
 **lastprivate (** *変数一覧* **)**  
  
 **削減 (** *演算子* **:***変数一覧* **)**   
  
 **nowait**  
  
 各セクションの後、**セクション**ディレクティブ、ですが、**セクション**ディレクティブは、最初のセクションでは省略可能です。 **セクション**ディレクティブはの構文上の範囲内でなければなりません。、**セクション**ディレクティブです。 暗黙的なバリアの末尾には、**セクション**しない限り、構築、 **nowait**が指定されています。  
  
 制限は、**セクション**ディレクティブは、次のとおり。  
  
-   A**セクション**の構文の範囲外ディレクティブが含まれなければ、**セクション**ディレクティブです。  
  
-   1 つだけ**nowait**句に表示できる、**セクション**ディレクティブです。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **プライベート**、 **firstprivate**、 **lastprivate**、および**削減**句を参照してください[セクション 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) [25] ページ。