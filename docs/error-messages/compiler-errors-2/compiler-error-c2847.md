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
ms.openlocfilehash: 004b3b4474593ac4350e35fd48309a271948a3ea
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

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

