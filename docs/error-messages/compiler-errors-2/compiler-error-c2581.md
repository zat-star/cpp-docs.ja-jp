---
title: "コンパイラ エラー C2581 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2581
dev_langs:
- C++
helpviewer_keywords:
- C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 591db0c4da45677205b8999d5661d44f12be5cb5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2581"></a>コンパイラ エラー C2581
'type': 静的 ' 演算子 = =' 関数は無効です  
  
 割り当て (`=`) 演算子は正しくとして宣言されて`static`です。 代入演算子にすることはできません`static`です。 詳細については、次を参照してください。[ユーザー定義の演算子 (C + + CLI)](../../dotnet/user-defined-operators-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 次の例では、C2581 を生成します。  
  
```  
// C2581.cpp  
// compile with: /clr /c  
ref struct Y {  
   static Y ^ operator = (Y^ me, int i);   // C2581  
   Y^ operator =(int i);   // OK  
};  
```