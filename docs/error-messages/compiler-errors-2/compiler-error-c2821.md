---
title: "コンパイラ エラー C2821 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2821
dev_langs:
- C++
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
caps.latest.revision: 8
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
translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 774c191bb3da3c5382c4aff7d48c8d6ae5ca7e68
ms.lasthandoff: 04/29/2017

---
# <a name="compiler-error-c2821"></a>{1&gt;コンパイラ エラー C2821&lt;1}
'operator new' への最初の仮パラメーターは 'unsigned int' である必要があります。  
  
最初の正式なパラメーター、 [new 演算子](../../standard-library/new-operators.md#op_new)unsigned にする必要があります`int`です。  
  
## <a name="example"></a>例  
 次の例では、C2821 が生成されます。  
  
```cpp  
// C2821.cpp  
// compile with: /c  
void * operator new( /* unsigned int,*/ void * );   // C2821  
void * operator new( unsigned int, void * );  
```
