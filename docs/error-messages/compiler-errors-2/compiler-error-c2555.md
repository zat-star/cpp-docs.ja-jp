---
title: "コンパイラ エラー C2555 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2555
dev_langs:
- C++
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c66b464ac38a46716fbed972939feef1273ad03d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2555"></a>コンパイラ エラー C2555
'class1::function1': 仮想関数をオーバーライドする型の戻り値は異なる 'class2::function2' の covariant ではありません  
  
 仮想関数と派生のオーバーライドする関数は、戻り値の型が同一のパラメーター リストにあります。 派生クラスでオーバーライドする関数は、その戻り値の型によってのみ、基底クラスの仮想関数を異なることはできません。  
  
 このエラーを解決するには、仮想関数が呼び出された後に、戻り値をキャストします。  
  
 /Clr でコンパイルする場合にも、このエラーを表示可能性があります。   たとえば、Visual c 次の c# の宣言と同じ。  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 is  
  
```  
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];  
```  
  
 C2555 の詳細については、サポート技術情報記事 Q240862 を参照してください。  
  
 次の例では、C2555 が生成されます。  
  
```  
// C2555.cpp  
// compile with: /c  
struct X {  
   virtual void func();  
};  
struct Y : X {  
   char func();  // C2555  
   void func2();   // OK  
};  
```