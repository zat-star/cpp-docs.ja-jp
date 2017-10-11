---
title: "コンパイラの警告 C4746 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1b88f51aa9365c0795c8d3d944ba9f3a8db059d9
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4746"></a>コンパイラの警告 C4746
揮発性アクセス '\<式 >' は/volatile: [iso (& a) #124; ms] 設定; _iso_volatile_load/store 組み込み関数の使用を検討してください。  
  
 Volatile 変数に直接アクセスするたびに、C4746 が生成されます。 開発者が指定されている特定の揮発性モデルの影響を受けるコードの場所を特定するのに役立つものでは (で制御できますが、 [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ オプション)。 具体的には、/volatile:ms を使用すると、コンパイラによって生成されたハードウェア メモリ バリアを検索するのに便利ですができます。  
  
 _Iso_volatile_load/store 組み込みは、揮発性のモデルに影響されることがなく明示的に揮発性メモリへのアクセスに使用できます。 これらの組み込みを使用しても、C4746 はトリガーされません。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。
