---
title: "コンパイラ エラー C3366 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3366
dev_langs:
- C++
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b862e606b86eca0a7eb7f2ad1e91f2776c8c0b23
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3366"></a>コンパイラ エラー C3366
'variable': 静的データ メンバーのマネージ配列または WinRTtypes はクラス定義内で定義する必要があります  
  
 WinRT または .NET のクラスまたはインターフェイスの静的メンバーをそのクラスまたはインターフェイスの定義外で参照しようとしました。  
  
 コンパイラは、(1 回のパスの後に、メタデータを出力するために) クラスの完全定義を認識する必要があり、静的データ メンバーをクラス内で初期化する必要があります。  
  
 たとえば、次の例では、C3366 を生成し、その修正方法を示しています。  
  
```  
// C3366.cpp  
// compile with: /clr /c  
ref class X {  
   public:  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```  

