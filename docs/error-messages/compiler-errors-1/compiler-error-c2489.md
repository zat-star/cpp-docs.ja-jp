---
title: "コンパイラ エラー C2489 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2489
dev_langs:
- C++
helpviewer_keywords:
- C2489
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b26d8efd166a79c00c4559c349fcc88fd01982e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2489"></a>コンパイラ エラー C2489
'identifier': 'naked' 関数では関数スコープで許可されません auto またはレジスタ変数の初期化  
  
 詳細については、次を参照してください。 [naked](../../cpp/naked-cpp.md)です。  
  
 次の例では、C2489 が生成されます。  
  
```  
// C2489.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   int i = 1;   // C2489  
   register int j = 1;   // C2489  
}  
```