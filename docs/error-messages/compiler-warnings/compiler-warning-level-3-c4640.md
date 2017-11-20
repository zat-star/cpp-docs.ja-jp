---
title: "コンパイラの警告 (レベル 3) C4640 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4640
dev_langs: C++
helpviewer_keywords: C4640
ms.assetid: f76871f6-e436-4c35-9793-d2f22f7e1c7f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 084b133b89c4ff4e90228814027fad6c021c0e33
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4640"></a>コンパイラの警告 (レベル 3) C4640
'instance': ローカル スタティック オブジェクトの構築がスレッド セーフではありません  
  
 オブジェクトの静的インスタンスは、スレッド セーフではありません。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
 次の例では、C4640 が生成されます。  
  
```  
// C4640.cpp  
// compile with: /W3  
#pragma warning(default:4640)  
  
class X {  
public:  
   X() {  
   }  
};  
  
void f() {  
   static X aX;   // C4640  
}  
  
int main() {  
   f();  
}  
```