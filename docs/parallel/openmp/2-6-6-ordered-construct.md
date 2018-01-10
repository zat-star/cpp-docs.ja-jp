---
title: "2.6.6 ordered コンストラクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e09a9d756cd068df9345034e26a4f152d3ac19fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="266-ordered-construct"></a>2.6.6 ordered コンストラクト
構造化ブロック次、**注文**ディレクティブが順次ループ内でのイテレーションが実行される順序で実行します。 構文、**注文**ディレクティブは、次のようにします。  
  
```  
#pragma omp ordered new-linestructured-block  
```  
  
 **注文**ディレクティブはの動的な範囲内である必要があります、**の**または**の並列**を構築します。 **の**または**の並列**するディレクティブ、**注文**コンストラクト バインドする必要がありますが、**順序付け**句で説明するよう指定[セクション 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) [11] ページ。 実行時に、**の**または**の並列**で構築、**注文**句、**注文**構造が厳密に実行される、ループの順次実行で実行される順序。  
  
 制限は、**注文**ディレクティブは、次のとおり。  
  
-   ループのイテレーション、**の**コンストラクト必要があります、同じ順序付けられたディレクティブは、2 回以上実行されず、1 つ以上実行する必要がありますいない**順序付け**ディレクティブです。