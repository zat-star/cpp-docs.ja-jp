---
title: "コンパイラ エラー C3904 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3904
dev_langs: C++
helpviewer_keywords: C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 31a6f728fdbfb9540245cf85879adef8c1827d2e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3904"></a>コンパイラ エラー C3904
'property_accessor': パラメーター番号を指定する必要があります  
  
 内のパラメーターの数を確認、`get`と`set`プロパティの次元に対してメソッドです。  
  
-   パラメーターの数、`get`メソッドのプロパティの次元の数と等しくかインデックス付けされていないプロパティを 0 にする必要があります。  
  
-   パラメーターの数、`set`メソッドは、いずれかを指定する必要があります、プロパティの次元数よりも詳細です。  
  
 詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C3904 を生成します。  
  
```  
// C3904.cpp  
// compile with: /clr /c  
ref class X {  
   property int P {  
      // set  
      void set();   // C3904  
      // try the following line instead  
      // void set(int);  
  
      // get  
      int get(int, int);   // C3904  
      // try the following line instead  
      // int get();  
   };  
};  
```  
  
## <a name="example"></a>例  
 次の例では、C3904 を生成します。  
  
```  
// C3904b.cpp  
// compile with: /clr /c  
ref struct X {  
   property int Q[double, double, float, float, void*, int] {  
      // set  
      void set(double, void*);   // C3904  
      // try the following line instead  
      // void set(double, double, float, float, void*, int, int);  
  
      // get  
      int get();   // C3904  
      // try the following line instead  
      // int get(double, double, float, float, void*, int);  
   }  
};  
```