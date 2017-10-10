---
title: "コンパイラ エラー C2891 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6c35294472fe4142e7e6689adfc5f5f71c27b664
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2891"></a>コンパイラ エラー C2891
'parameter': テンプレート パラメーターのアドレスを取得できません  
  
 左辺値である場合を除き、テンプレート パラメーターのアドレスを取得できません。 型パラメーターは、アドレスがないために、左辺値ではありません。 また、左辺値ではないテンプレート パラメーター リスト内の非型の値には、アドレスがありません。 これは、テンプレート パラメーターとして渡された値がコンパイラによって生成されたテンプレート引数のコピーであるために、コンパイラ エラー C2891 を原因となったコードの例です。  
  
```  
template <int i> int* f() { return &i; }  
```  
  
 テンプレート パラメーターなど、参照型の左辺値であることができますが、アドレスを取得します。  
  
```  
template <int& r> int* f() { return &r; }  
```  
  
 このエラーを修正するにはなりませんテンプレート パラメーターのアドレスは左辺値である場合を除き。
