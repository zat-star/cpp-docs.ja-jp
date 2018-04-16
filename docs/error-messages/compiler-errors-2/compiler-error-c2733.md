---
title: "コンパイラ エラー C2733 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2733
dev_langs:
- C++
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb0c21850d93a39047bacfe38592e381e9fb5918
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2733"></a>コンパイラ エラー C2733
C リンケージの 2 番目のオーバー ロードされた関数 'function' が許可されていません  
  
 1 つ以上のオーバー ロードされた関数は C リンケージで宣言します。 C リンケージを使用する場合、指定された関数の 1 つしかは外部できます。 装飾されていない名前が同じであるオーバー ロードされた関数からは、C プログラムで使用できません。  
  
 次の例では、C2733 が生成されます。  
  
```  
// C2733.cpp  
extern "C" {  
   void F1(int);  
}  
  
extern "C" {  
   void F1();   // C2733  
   // try the following line instead  
   // void F2();  
}  
```