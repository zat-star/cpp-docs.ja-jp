---
title: "コンパイラ エラー C3320 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3320
dev_langs:
- C++
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c729bf63fae7a7181496e1901dda1d8ac5bdfa50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3320"></a>コンパイラ エラー C3320
'type': 型には、モジュール 'name' プロパティと同じ名前を指定することはできません  
  
渡されるパラメーターとして、エクスポートされたユーザー定義型 (UDT)、構造体型、クラス、列挙型、または共用体の場合が、同じ名前を持つことはできません、[モジュール](../../windows/module-cpp.md)属性の name プロパティです。  
  
## <a name="example"></a>例  
次の例では C3320 が生成されます。  
  
```cpp  
// C3320.cpp  
#include "unknwn.h"  
[module(name="xx")];  
  
[export] struct xx {   // C3320  
// Try the following line instead  
// [export] struct yy {  
   int i;  
};  
```