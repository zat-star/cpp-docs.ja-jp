---
title: "コンパイラ エラー C3809 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3809
dev_langs:
- C++
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ef105c573e9db828d612589106d6aa31d915f664
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3809"></a>コンパイラ エラー C3809
'class' : マネージ型または WinRT 型にフレンド関数、クラス、インターフェイスを含めることはできません。  
  
 マネージ型と Windows ランタイム型では、フレンドは許可されません。 このエラーを修復するには、マネージ型または Windows ランタイム型内でフレンドを宣言しないようにします。  
  
 次の例では、C3809 エラーが生成されます。  
  
```  
// C3809a.cpp  
// compile with: /clr  
ref class A {};  
  
ref class B  
{  
public:  
   friend ref class A;   // C3809  
};  
  
int main()  
{  
}  
```
