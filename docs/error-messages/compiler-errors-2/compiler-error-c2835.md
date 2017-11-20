---
title: "コンパイラ エラー C2835 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2835
dev_langs: C++
helpviewer_keywords: C2835
ms.assetid: 41c70630-983f-4da2-8342-513cf48b0519
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 08a09c0ea495fcaff01527b0c4af720f2a831db5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2835"></a>コンパイラ エラー C2835
ユーザー定義変換 'type' が仮パラメーターを受け取らない  
  
 ユーザー定義型の変換には、仮パラメーターを受け取ることはできません。  
  
 次の例では、C2835 が生成されます。  
  
```  
// C2835.cpp  
class A {  
public:  
   char v_char;  
  
   A() {   
      v_char = 'A';   
   };  
   operator char(char a) {   // C2835  
   // try the following line instead  
   // operator char() {     
      return v_char + 1;   
   };  
};  
  
int main() {  
   A a;  
}  
```