---
title: "コンパイラ エラー C3373 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3373
dev_langs: C++
helpviewer_keywords: C3373
ms.assetid: 6e7586c3-1a15-4773-ad20-f90090a400dc
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5de888c83ca91d9e05cd5521d487f9c8d4e3492f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3373"></a>コンパイラ エラー C3373
属性 'attribute' はコクラス以外で引数を必要としません  
  
 2 つ以上の C++ コンストラクトに適用できる属性もありますが、属性の引数の使用は、一部のコンストラクトに限られる場合があります。  
  
 次の例では C3373 が生成されます。  
  
```  
// C3373.cpp  
#include <windows.h>  
  
[module(name="MyModule")];  
  
[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]  
__interface IMyIface  
{  
   // arguments to source and restricted are not allowed when  
   // these attributes are applied to an interface  
   [source(IMyIface)] HRESULT f1();  
   [restricted(IMyIface)] HRESULT f2(); // C3373  
};  
  
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f) ]  
class CMyClass : public IMyIface {  
};  
  
int main() {  
}  
```