---
title: "コンパイラの警告 C4867 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4867
dev_langs:
- C++
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
caps.latest.revision: 16
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
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 86437fca7bfeef662bef9fe8311fb746a661264d
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4867"></a>コンパイラの警告 C4867
'function': 関数呼び出しの引数リストがありません。'call' を使用して、メンバーへのポインターを作成するには  
  
 メンバー関数へのポインターが正しく初期化されませんでした。  
  
 この警告は、Visual C 2005 で行ったコンパイラへの準拠作業の結果として生成することができます: メンバーへのポインターに対する準拠が強化されました。  Visual C 2005 より前にコンパイルされたコードは、C4867 を今すぐ生成されます。  
  
 この警告は、常にエラーとして表示されます。 使用して、[警告](../../preprocessor/warning.md)プラグマをこの警告を無効にします。 C4867 および MFC/ATL の詳細については、次を参照してください。 [_ATL_ENABLE_PTM_WARNING](http://msdn.microsoft.com/Library/00b9ff5c-9834-4c40-911e-ee88d512c4af)します。  
  
## <a name="example"></a>例  
 次の例では、C4867 が生成されます。  
  
```  
// C4867.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b = {f};   // C4867  
      B b2 = {&A::f};   // OK  
   }  
};  
```
