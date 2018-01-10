---
title: "致命的なエラー C1026 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1026
dev_langs: C++
helpviewer_keywords: C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 206e9843fd8566f4f595a46918548af14f119439
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1026"></a>致命的なエラー C1026
プログラムの解析でコンパイラ内でスタック オーバーフローが発生しました。プログラムが複雑すぎます。  
  
 プログラムの解析に必要な領域には、コンパイラ スタック オーバーフローが発生します。  
  
 式の複雑さを軽減するには。  
  
-   内の入れ子構造の減少`for`と`switch`ステートメントです。 別の関数により深く入れ子になったステートメントを配置します。  
  
-   コンマ演算子や関数呼び出しを含む長い式に分割することです。