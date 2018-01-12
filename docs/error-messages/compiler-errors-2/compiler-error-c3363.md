---
title: "コンパイラ エラー C3363 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3363
dev_langs: C++
helpviewer_keywords: C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dbdd31f9ecdc6f458f09d0561465cdf21cdde250
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3363"></a>コンパイラ エラー C3363
'type': 'typeid' のみを型に適用できます  
  
 [typeid](../../windows/typeid-cpp-component-extensions.md) 演算子が正しく使用されていません。  
  
## <a name="example"></a>例  
 次の例では C3363 が生成されます。  
  
```  
// C3363.cpp  
// compile with: /clr  
int main() {  
   System::typeid;   // C3363  
}  
```