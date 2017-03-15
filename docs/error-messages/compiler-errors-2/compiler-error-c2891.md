---
title: "コンパイラ エラー C2891 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 629d1c0b98f1bf6a813bd28f25c4e5afc0e7b367
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2891"></a>コンパイラ エラー C2891
'パラメーター': テンプレート パラメーターのアドレスを受け取ることはできません  
  
 左辺値である場合を除き、テンプレート パラメーターのアドレスを受け取ることはできません。 型パラメーターは、アドレスがないために、左辺値ではありません。 また、左辺値ではない、テンプレート パラメーター リスト内の非型の値には、アドレスはありません。 これは、テンプレート パラメーターとして渡される値がテンプレート引数のコンパイラが生成したコピーであるために、コンパイラ エラー C2891 を発生するコードの例です。  
  
```  
template <int i> int* f() { return &i; }  
```  
  
 テンプレート パラメーターなど、参照型の左辺値であることができます、アドレスを採用しています。  
  
```  
template <int& r> int* f() { return &r; }  
```  
  
 このエラーを修正するには、なりませんテンプレート パラメーターのアドレスを左辺値でない限り。
