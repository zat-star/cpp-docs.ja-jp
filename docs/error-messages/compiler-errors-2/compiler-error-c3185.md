---
title: "コンパイラ エラー C3185 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3185
dev_langs: C++
helpviewer_keywords: C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9defaa122e998d9b5cc1ab46224bdf04b8027b6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3185"></a>コンパイラ エラー C3185
マネージまたは WinRT 型 'type' で 'typeid' が使用されました。代わりに 'operator' を使用してください  
  
 適用することはできません、 [typeid](../../cpp/typeid-operator.md)演算子をマネージまたは WinRT 型; を使用して[typeid](../../windows/typeid-cpp-component-extensions.md)代わりにします。  
  
 次の例は C3185 を生成し、その修正方法を示しています。  
  
```  
// C3185a.cpp  
// compile with: /clr  
ref class Base {};  
ref class Derived : public Base {};  
  
int main() {  
   Derived ^ pd = gcnew Derived;  
   Base ^pb = pd;  
   const type_info & t1 = typeid(pb);   // C3185  
   System::Type ^ MyType = Base::typeid;   // OK  
};  
```  
