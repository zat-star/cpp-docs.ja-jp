---
title: "コンパイラ エラー C3181 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3181
dev_langs:
- C++
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
caps.latest.revision: 10
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 4229a9d9811bad46035451c5d64b7ed06da476d2
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3181"></a>コンパイラ エラー C3181
'type': 演算子のオペランドが無効です  
  
無効なパラメーターが渡された、 [typeid](../../windows/typeid-cpp-component-extensions.md)演算子。 パラメーターは、マネージ型である必要があります。  
  
コンパイラでは、共通言語ランタイムの型にマップするネイティブ型のエイリアスが使用されることに注意してください。  
  
次の例では、c3181 エラーが生成されます。  
  
```  
// C3181a.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181  
   Type ^pType2 = int::typeid;   // OK  
}  
```  

