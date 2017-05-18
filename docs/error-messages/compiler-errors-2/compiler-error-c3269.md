---
title: "コンパイラ エラー C3269 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3269
dev_langs:
- C++
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
caps.latest.revision: 9
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
ms.openlocfilehash: 7349909f413d489546023da498ffdbc8fc1c450a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3269"></a>コンパイラ エラー C3269
'function': マネージまたは WinRTtype のメンバー関数は、'…' で宣言することはできません  
  
マネージ クラスと WinRT クラスのメンバー関数では可変長のパラメーター リストを宣言できません。  
  
次の例では C3269 を生成し、その修正方法を示しています。  
  
```  
// C3269_2.cpp  
// compile with: /clr  
  
ref struct A  
{  
   void func(int i, ...)   // C3269  
   // try the following line instead  
   // void func(int i )  
   {  
   }  
};  
  
int main()  
{  
}  
```  

