---
title: "コンパイラ エラー C3836 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3836
dev_langs:
- C++
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
caps.latest.revision: 8
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
ms.openlocfilehash: 0708b8c9bf59e1c2ea3751fbb91192d6b873d8ec
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3836"></a>コンパイラ エラー C3836
静的コンス トラクターは、メンバー初期化子リストを含めることできません。  
  
 マネージ クラスには、静的コンス トラクターを持つメンバー初期化リストを持つことはできません。 静的クラス コンス トラクターは、クラスの初期化、静的データ メンバーの初期化を行う共通言語ランタイムによって呼び出されます。  
  
## <a name="example"></a>例  
 次の例では、c3836 エラーが生成されます。  
  
```  
// C3836a.cpp  
// compile with: /clr  
ref class M  
{  
   static int s_i;  
  
public:  
   static M() :  s_i(1234)   // C3836, delete initializer to resolve  
   {  
   }  
};  
  
int main()  
{  
}  
```  

