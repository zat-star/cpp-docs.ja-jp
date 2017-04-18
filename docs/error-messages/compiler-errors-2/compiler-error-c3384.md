---
title: "コンパイラ エラー C3384 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3384
dev_langs:
- C++
helpviewer_keywords:
- C3384
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 3aa2f068dd11441bdb1e5e3922041ef4213fd2d8
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3384"></a>コンパイラ エラー C3384
'type_parameter': 値の制約および ref 制約を同時に使用することはできません  
  
 ジェネリック型を `value class` と `ref class`の両方に制限することはできません。  
  
 参照してください[ジェネリック型パラメーターの制約 (C + + CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では C3384 が生成されます。  
  
```  
// C3384.cpp  
// compile with: /c /clr  
generic <typename T>  
where T : ref class  
where T : value class   // C3384  
ref class List {};  
```
