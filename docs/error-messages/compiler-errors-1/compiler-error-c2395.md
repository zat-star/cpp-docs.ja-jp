---
title: "コンパイラ エラー C2395 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2395
dev_langs:
- C++
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
caps.latest.revision: 12
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
ms.openlocfilehash: 62ea1fb0e013f46785e08c4cf2c1711338ac4c6a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2395"></a>コンパイラ エラー C2395
'your_type::operator'op'' : CLR または WinRT 演算子が無効です。 少なくとも&1; つのパラメーターが次の型である必要があります: 'T'、'T%'、'T&'、'T^'、'T^%'、'T^&' (T = 'your_type')。  
  
 Windows ランタイムまたはマネージ型の演算子に、演算子の戻り値の型と同じ型を持つ&1; つ以上のパラメーターがありません。  
  
 次の例では、C2395 を生成し、その修正方法を示しています。  
  
```  
// C2395.cpp  
// compile with: /clr /c  
value struct V {  
   static V operator *(int i, char c);   // C2395  
  
   // OK  
   static V operator *(V v, char c);  
   // or  
   static V operator *(int i, V& rv);  
};  
```
