---
title: コンパイラ エラー C3638 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3638
dev_langs:
- C++
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 879ccb667ce766a24cb9666ec74fb89728c9d8d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3638"></a>コンパイラ エラー C3638
'operator': 標準ボックス化とボックス化解除変換演算子を再定義することはできません  
  
 コンパイラでは、暗黙的なボックス化をサポートするために各マネージ クラスの変換演算子を定義します。 この演算子は再定義することはできません。  
  
 詳細については、次を参照してください。[暗黙的なボックス化](../../windows/boxing-cpp-component-extensions.md)です。  
  
 次の例では、C3638 が生成されます。  
  
```  
// C3638.cpp  
// compile with: /clr  
value struct V {  
   V(){}  
   static operator V^(V);   // C3638  
};  
  
int main() {  
   V myV;  
   V ^ pmyV = myV;   // operator supports implicit boxing  
}  
```