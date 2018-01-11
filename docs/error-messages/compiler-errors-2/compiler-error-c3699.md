---
title: "コンパイラ エラー C3699 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3699
dev_langs: C++
helpviewer_keywords: C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2d4b89c2b91aab1869c97731731ed03a363767e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3699"></a>コンパイラ エラー C3699
'operator': 型 'type' でこの間接指定を使用することはできません  
  
 許可されていない間接指定を使用しようとしましたが`type`です。  
  
## <a name="example"></a>例  
 次の例では、C3699 を生成します。  
  
```  
// C3699.cpp  
// compile with: /clr /c  
using namespace System;  
int main() {  
   String * s;   // C3699  
   // try the following line instead  
   // String ^ s2;  
}  
```  
  
## <a name="example"></a>例  
 Trivial プロパティには、参照型を持つことはできません。 詳細については、「 [property](../../windows/property-cpp-component-extensions.md) 」を参照してください。 次の例では、C3699 を生成します。  
  
```  
// C3699_b.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String % x;   // C3699  
   property System::String ^ y;   // OK  
};  
```  
  
## <a name="example"></a>例  
 「ポインターへのポインター」構文の該当するショートカットは、追跡参照にハンドルです。 次の例では、C3699 を生成します。  
  
```  
// C3699_c.cpp  
// compile with: /clr /c  
using namespace System;  
void Test(String ^^ i);   // C3699  
void Test2(String ^% i);  
```