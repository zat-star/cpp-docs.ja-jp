---
title: "コンパイラ エラー C3408 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3408
dev_langs:
- C++
helpviewer_keywords:
- C3408
ms.assetid: 1f5ea979-fb1e-4214-b310-6fd6ca8249b1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1a9ae9ec7324b55153f29da94b6a1e08c9264cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3408"></a>コンパイラ エラー C3408
'attribute': テンプレート定義で、属性を指定することはできません  
  
 テンプレート定義に属性を適用することはできません。  
  
## <a name="example"></a>例  
 次の例では C3408 が生成されます。  
  
```  
// C3408.cpp  
// compile with: /c  
template <class T> struct PTS {  
   enum {  
      IsPointer = 0,  
      IsPointerToDataMember = 0  
   };  
};  
  
template <class T>   
[coclass]   // C3408  
struct PTS<T*> {  
   enum {  
      IsPointer = 1,  
      IsPointerToDataMember = 0  
   };  
};  
  
template   
<class T, class U>   
struct PTS<T U::*> {  
   enum {  
      IsPointer = 1,  
      IsPointerToDataMember = 1  
   };  
};  
  
struct S{};  
  
extern "C" int printf(const char*,...);  
  
int main() {  
   S s, *pS;  
   int S::*ptm;  
  
   printf("PTS<S>::IsPointer == %d PTS<S>::IsPointerToDataMember == %d\n", PTS<S>::IsPointer, PTS<S>:: IsPointerToDataMember);  
   printf("PTS<S*>::IsPointer == %d PTS<S*>::IsPointerToDataMember == %d\n", PTS<S*>::IsPointer, PTS<S*>:: IsPointerToDataMember);  
   printf("PTS<int S::*>::IsPointer == %d PTS<int S::*>::IsPointerToDataMember == %d\n", PTS<int S::*>::IsPointer, PTS<int S::*>:: IsPointerToDataMember);  
}  
```