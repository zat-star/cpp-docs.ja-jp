---
title: "コンパイラ エラー C3266 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3266
dev_langs: C++
helpviewer_keywords: C3266
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2d0de492ec014fd71abd81097717bbfab3ae5a31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3266"></a>コンパイラ エラー C3266
'class' : クラス コンストラクターは 'void' パラメーター リストを必要とします  
  
/clr プログラミングを使用するクラスのクラス コンストラクターは、パラメーターを受け取ることはできません。  
  
次の例では C3266 が生成されます。  
  
```  
// C3266.cpp  
// compile with: /clr  
  
ref class X {  
   static X(int i) { // C3266  
   // try the following line instead  
   // static X() {  
   }  
};  
  
int main() {  
}  
```  
