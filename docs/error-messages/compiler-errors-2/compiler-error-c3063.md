---
title: "コンパイラ エラー C3063 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3063
dev_langs:
- C++
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: ce6a597e0246cee5c62dd6612d48fe4946505e77
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3063"></a>コンパイラ エラー C3063
演算子 'operator': すべてのオペランドが同じ列挙型を持つ必要があります  
  
列挙子の演算子を使用する場合は、両方のオペランドが列挙型でなければなりません。 詳細については、次を参照してください。[方法: 定義および C + で列挙型を使用する/cli CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)します。  
  
## <a name="example"></a>例  
次の例では、C3063 を生成し、その修正方法を示しています。  
  
```  
// C3063.cpp  
// compile with: /clr  
enum class E { a, b } e, mask;  
int main() {  
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)  
  
   if ( ( e & mask ) != E() )   // OK  
      ;  
}  
```
