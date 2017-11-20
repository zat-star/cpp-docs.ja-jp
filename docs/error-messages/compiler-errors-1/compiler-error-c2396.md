---
title: "コンパイラ エラー C2396 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2396
dev_langs: C++
helpviewer_keywords: C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20eca11d402265bbc81d61a8079ae9975cceef67
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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