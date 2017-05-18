---
title: "コンパイラ エラー C2787 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2787
dev_langs:
- C++
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: d421b339df28bcccdfcba2c9b297f1cd5a16915d
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2787"></a>コンパイラ エラー C2787
'identifier': このオブジェクトに関連付けられた GUID はありません。  
  
 [_ _Uuidof](../../cpp/uuidof-operator.md)演算子は、アタッチされている GUID またはユーザー定義型のオブジェクトと、ユーザー定義型を取ります。 このエラーは、引数が GUID を持つユーザー定義型である場合に発生しません。  
  
 次の例では、c2787 エラーが生成されます。  
  
```  
// C2787.cpp  
#include <windows.h>  
struct F {};  
  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;  
  
int main() {  
   __uuidof(F);   // C2787  
   __uuidof(F2);   // OK  
}  
```
