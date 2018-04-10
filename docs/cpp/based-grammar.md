---
title: _ _based 文法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a2cb2929fa595ad13746ea929217f41272a8189
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="based-grammar"></a>__based 文法
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 ベースとなるアドレス指定は、オブジェクトが割り当てられるセグメントを詳細に制御する必要がある場合に便利です (静的および動的ベースのデータ)。  
  
 32 ビットおよび 64 ビット コンパイルで受け入れられるベースとなるアドレス指定の唯一の形式は、32 ビットまたは 64 ビット ベースへの 32 ビットまたは 64 ビットの変位を含む型を定義する、または `void` に基づく、「ポインターをベースとする」ものです。  
  
## <a name="grammar"></a>文法  
 *ベース範囲修飾子*:  
 **_ _based (***ベース式***)**   
  
 *基本式*:  
 *based-variablebased-abstract-declaratorsegment-namesegment-cast*  
  
 *ベース変数*:  
 *identifier*  
  
 *ベース-抽象宣言子*:  
 *抽象宣言子*  
  
 *基本型*:  
 *型名*  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [ベース ポインター](../cpp/based-pointers-cpp.md)