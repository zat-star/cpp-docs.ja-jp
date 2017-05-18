---
title: "コンパイラの警告 C4867 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: a052194893db90177b88eea8f80435777ae37773
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4867"></a>コンパイラの警告 C4867
'function': 関数呼び出しの引数リストがありません。'call' を使用して、メンバーへのポインターを作成するには  
  
 メンバー関数へのポインターが正しく初期化されていません。  
  
 この警告は、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成できます。 準拠が強化されたメンバーへのポインター。  Visual C 2005 より前にコンパイルされたコードには、今すぐ C4867 が生成されます。  
  
 この警告は、常にエラーとして表示されます。 使用して、[警告](../../preprocessor/warning.md)プラグマをこの警告を無効にします。 C4867 および MFC と ATL の詳細については、次を参照してください。 [_ATL_ENABLE_PTM_WARNING](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning)です。  
  
## <a name="example"></a>例  
 次の例では、C4867 を生成します。  
  
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
