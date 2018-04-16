---
title: "コンパイラ エラー C2394 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2394
dev_langs:
- C++
helpviewer_keywords:
- C2394
ms.assetid: 653fa9a0-29b3-48aa-bc01-82f98f717a2b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d9cdfb2ace09bfc3aae4fa4afabd0d45117a80a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2394"></a>コンパイラ エラー C2394
'your_type::operator'op'": CLR または WinRToperator 有効ではありません。 少なくとも 1 つのパラメーターが次の型である必要があります: 'T^'、'T^%'、'T^&' (T = 'your_type')。  
  
 Windows ランタイムまたはマネージ型の演算子に、演算子の戻り値の型と同じ型を持つ 1 つ以上のパラメーターがありません。  
  
 次の例では C2394 が生成されます。  
  
```  
// C2394.cpp  
// compile with: /clr /c  
ref struct Y {  
   static Y^ operator -(int i, char c);   // C2394  
  
   // OK  
   static Y^ operator -(Y^ hY, char c);  
   // or  
   static Y^ operator -(int i, Y^& rhY);  
};  
```