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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 930114bfb06019f13b4f44cc51b72922237a62f6
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3366"></a>コンパイラ エラー C3366
'variable': の静的データ メンバーの管理や WinRTtypes はクラス定義内で定義する必要があります  
  
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

