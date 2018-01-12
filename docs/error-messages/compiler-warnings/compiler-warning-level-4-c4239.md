---
title: "コンパイラの警告 (レベル 4) C4239 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4239
dev_langs: C++
helpviewer_keywords: C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 18f1c6d700de0c621ebde02c7dcb2817091677cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4239"></a>コンパイラの警告 (レベル 4) C4239
標準の拡張機能を使用します 'token': 'type' から 'type' への変換。  
  
 C++ 標準では、この型の変換は許可されていないが、許可されている拡張機能としては、ここです。 この警告では、少なくとも 1 つの行の説明に違反して言語のルールを記述する常が続きます。  
  
## <a name="example"></a>例  
 次の例では、C4239 が生成されます。  
  
```  
// C4239.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
void func(void) {  
   C & rC = C();   // C4239  
   const C & rC2 = C();   // OK  
   rC2;  
}  
```  
  
## <a name="example"></a>例  
 整数型から列挙型への変換は厳密には許可されません。  
  
 次の例では、C4239 が生成されます。  
  
```  
// C4239b.cpp  
// compile with: /W4 /c  
enum E { value };   
struct S {   
   E e : 2;   
} s = { 5 };   // C4239   
// try the following line instead  
// } s = { (E)5 };  
```