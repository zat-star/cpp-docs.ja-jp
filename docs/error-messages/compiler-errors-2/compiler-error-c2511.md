---
title: "コンパイラ エラー C2511 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2511
dev_langs: C++
helpviewer_keywords: C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1ba01f808fb4dd618291777c1da7490b3b95af3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2511"></a>コンパイラ エラー C2511
'identifier': オーバー ロード メンバー関数の 'class' に見つかりませんでした  
  
 指定されたパラメーターでは、関数のバージョンは宣言されていません。  以下の原因が考えられます。  
  
1.  不適切なパラメーターは、関数に渡されます。  
  
2.  間違った順序でパラメーターが渡されます。  
  
3.  パラメーター名のスペルが間違っています。  
  
 次の例では、C2511 が生成されます。  
  
```  
// C2511.cpp  
// compile with: /c  
class C {  
   int c_2;  
   int Func(char *, char *);  
};  
  
int C::Func(char *, char *, int i) {   // C2511  
// try the following line instead  
// int C::Func(char *, char *) {  
   return 0;  
}  
```