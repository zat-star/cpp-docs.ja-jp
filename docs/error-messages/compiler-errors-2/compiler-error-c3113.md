---
title: "コンパイラ エラー C3113 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3113
dev_langs:
- C++
helpviewer_keywords:
- C3113
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 53d13466368ce1b9e473c2c2fce1c96f3d9a0f81
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3113"></a>コンパイラ エラー C3113
'structure' をテンプレートまたはジェネリックにすることはできません。  
  
 ジェネリック インターフェイスまたは列挙型から、クラス テンプレートまたはクラスを作成しようとしました。  
  
 次の例では、c3113 エラーが生成されます。  
  
```  
// C3113.cpp  
// compile with: /c  
template <class T>   
enum E {};   // C3113  
// try the following line instead  
// class MyClass{};  
```
