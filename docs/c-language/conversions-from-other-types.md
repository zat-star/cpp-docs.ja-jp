---
title: "他の型からの変換 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ed56c0c9ab3186200d3cbb47224dedc60adddb2f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="conversions-from-other-types"></a>Conversions from Other Types (他の型からの変換)
`enum` 値は、定義上、`int` 値であるため、`enum` 値との相互変換は `int` 型との相互変換と同じです。 Microsoft C コンパイラの場合、整数は **long** と同じです。  
  
 **Microsoft 固有の仕様**  
  
 構造体型または共用体型の間の変換はできません。  
  
 任意の値を `void` 型に変換できますが、このような変換の結果は、式ステートメントなど、式の値が破棄されるコンテキストでのみ使用できます。  
  
 `void` 型には定義上、値がありません。 したがって、他の型に変換できず、他の型を代入によって `void` に変換することはできません。 ただし、「[型キャスト変換](../c-language/type-cast-conversions.md)」で説明されているように、値を明示的に `void` 型にキャストすることができます。  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [代入の変換](../c-language/assignment-conversions.md)