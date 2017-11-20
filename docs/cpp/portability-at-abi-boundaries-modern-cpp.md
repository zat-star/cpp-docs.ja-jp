---
title: "ABI の境界 (Modern C) での移植性 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 397c3faeeed85633f949c331c9be12c6a8a5a46b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="portability-at-abi-boundaries-modern-c"></a>ABI の境界での移植性 (Modern C++)
バイナリ インターフェイスの境界で十分にポータブル型と規則を使用します。 "ポータブル type"は、C の組み込み型または C の組み込み型のみを含む構造体です。 クラスの型は、呼び出し元と呼び出し先が一致レイアウト、規則などを呼び出すことときにのみ使用できます。これは、同じコンパイラおよびコンパイラ設定で両方がコンパイルされるときにのみ可能です。  
  
## <a name="how-to-flatten-a-class-for-c-portability"></a>C の移植性のクラスを平坦化する方法  
 呼び出し元が別のコンパイラ/言語でコンパイルすることがありますするには、「統合」、 **extern"C"**の特定の呼び出し規約と API:  
  
```cpp  
// class widget {  
//   widget();  
//   ~widget();  
//   double method( int, gadget& );  
// };  
extern "C" {        // functions using explicit "this"  
   struct widget;   // opaque type (forward declaration only)  
   widget* STDCALL widget_create();      // constructor creates new "this"  
   void STDCALL widget_destroy(widget*); // destructor consumes "this"  
   double STDCALL widget_method(widget*, int, gadget*); // method uses "this"  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)