---
title: "コンパイラ エラー C3136 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3136
dev_langs:
- C++
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9e6a8e3c958c6c1293b20451f632910001ef24f2
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3136"></a>コンパイラ エラー C3136
'interface': COM インターフェイスは、他の COM インターフェイスからのみ継承できます、'interface' は、COM インターフェイスではありません  
  
 適用されているインターフェイス、[インターフェイス属性](../../windows/interface-attributes.md)COM インターフェイスではないインターフェイスから継承します。 COM インターフェイスの最終的な継承`IUnknown`です。 インターフェイス属性に続く任意のインターフェイスは、COM インターフェイスです。  
  
 次の例では、C3136 が生成されます。  
  
```  
// C3136.cpp  
#include "unknwn.h"  
  
__interface A   // C3136  
// try the following line instead  
// _interface A : IUnknown  
{  
   int a();  
};  
  
[object]  
__interface B : A  
{  
   int aa();  
};  
```
