---
title: "致命的なエラー C1026 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1026
dev_langs:
- C++
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 187cfc1a59fc40a721be09aef9e78ef36c68f66a
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1026"></a>致命的なエラー C1026
プログラムの解析でコンパイラ内でスタック オーバーフローが発生しました。プログラムが複雑すぎます。  
  
 プログラムの解析に必要な領域には、コンパイラ スタック オーバーフローが発生します。  
  
 式の複雑さを軽減するには。  
  
-   内の入れ子構造の減少`for`と`switch`ステートメントです。 別の関数により深く入れ子になったステートメントを配置します。  
  
-   コンマ演算子や関数呼び出しを含む長い式に分割することです。
