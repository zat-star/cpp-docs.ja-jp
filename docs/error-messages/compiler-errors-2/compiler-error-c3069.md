---
title: "コンパイラ エラー C3069 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3069
dev_langs:
- C++
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6470ec9177ee1478c691fa3afb2c5e997e16be8a
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3069"></a>コンパイラ エラー C3069
'operator': 列挙型には使用できません  
  
 演算子は CLR 列挙体ではサポートされていません。  詳細については、次を参照してください。[する方法: 定義および C で列挙型を使用する + CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 次の例では C3069 が生成されます。  
  
```  
// C3069.cpp  
// compile with: /clr  
enum struct E { e1 };  
enum F { f1 };  
  
int main() {  
   E e = E::e1;  
   bool tf;  
   tf = !e;   // C3069  
  
   // supported for native enums  
   F f = f1;  
   tf = !f;  
}  
```
