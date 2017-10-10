---
title: "コンパイラ エラー C2847 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2847
dev_langs:
- C++
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8406ea786def9c3241a0ae1de8743d53e91f96cd
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2847"></a>コンパイラ エラー C2847
マネージ型または WinRT 型の 'class' に対して sizeof を使用できません  
  
 [Sizeof](../../cpp/sizeof-operator.md)演算子は、コンパイル時にオブジェクトの値を取得します。 マネージまたは WinRT のクラス、インターフェイス、または値型のサイズは、動的であるため、コンパイル時に確定できません。  
  
 たとえば、次の例では C2847 が生成されます。  
  
```  
// C2847.cpp  
// compile with: /clr  
ref class A {};  
  
int main() {  
   A ^ xA = gcnew A;  
   sizeof(*xA);   // C2847 cannot use sizeof on managed object  
}  
```  

