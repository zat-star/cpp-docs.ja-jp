---
title: "キャスト演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- cast operators
- type casts, operators
- operators [C++], cast
- type conversion, cast operators
ms.assetid: 43b90bbd-39ef-43e6-ae5d-e8a67a01de40
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3f922bb052d6a69bc8a051769bc552b1f2653de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cast-operators"></a>キャスト演算子
型キャストは、特定の状況におけるオブジェクトの型の明示的な変換方法を示します。  
  
## <a name="syntax"></a>構文  
 *cast-expression*:  
 *unary-expression*  
  
 **(**  *type-name*  **)**  *cast-expression*  
  
 コンパイラは、型キャストが実行された後で、*cast-expression* を *type-name* 型として処理します。 キャストを使用すると、スカラー型オブジェクトの型を他のスカラー型との間で変換できます。 明示的な型キャストは、暗黙的な変換の結果が決定されるときと同じ規則により制限されます。これについては、「[代入変換](../c-language/assignment-conversions.md)」で説明しています。 特定の型の実際のサイズまたは表現から、キャストにさらに制限が課せられる場合があります。 整数型の実際のサイズについては、「[基本型の格納](../c-language/storage-of-basic-types.md)」をご覧ください。 型キャストの詳細については、「[型キャスト変換](../c-language/type-cast-conversions.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [キャスト演算子: ()](../cpp/cast-operator-parens.md)