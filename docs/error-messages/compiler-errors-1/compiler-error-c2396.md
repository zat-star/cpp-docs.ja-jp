---
title: "コンパイラ エラー C2396 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2396
dev_langs:
- C++
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3cabcb0acf6f9b0a476df35de887fc3c9e0efb01
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2396"></a>コンパイラ エラー C2396
' your_type::operator'type ': 無効な CLR または WinRT のユーザー定義の変換の functionnot します。 変換元または変換先が次の値でなければなりません: 'T^'、'T^%'、'T^&' (ここで T = 'your_type')  
  
 Windows ランタイム型またはマネージ型の変換関数に、変換関数が含まれる型と同じ型を持つ 1 つ以上のパラメーターがありません。  
  
 次の例では、C2396 を生成し、その修正方法を示しています。  
  
```  
// C2396.cpp  
// compile with: /clr /c  
  
ref struct Y {  
   static operator int(char c);   // C2396  
  
   // OK  
   static operator int(Y^ hY);  
   // or  
   static operator Y^(char c);  
};  
```