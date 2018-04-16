---
title: "コンパイラ エラー C2758 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2758
dev_langs:
- C++
helpviewer_keywords:
- C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a67a978883153e0de81e864bf01e8cf9ee2e13c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2758"></a>コンパイラ エラー C2758
'member': 参照型のメンバーは初期化する必要があります  
  
 初期化子リスト内の参照型のメンバーがコンストラクターによって初期化されていない場合、コンパイラ エラー C2758 が発生します。 コンパイラはそのメンバーを未定義のままにします。 参照型のメンバー変数は、コンストラクターの初期化リストで宣言されるか値を指定されるときに初期化する必要があります。  
  
 次の例では C2758 エラーが生成されます。  
  
```  
// C2758.cpp  
// Compile by using: cl /W3 /c C2758.cpp  
struct A {  
   const int i;  
  
   A(int n) { };   // C2758  
   // try the following line instead  
   // A(int n) : i{n} {};  
};  
```