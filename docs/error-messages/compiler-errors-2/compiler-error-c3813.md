---
title: "コンパイラ エラー C3813 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3813
dev_langs:
- C++
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cabe753691b3d72ede25f0c25404d73fb63ceba8
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3813"></a>コンパイラ エラー C3813
プロパティ宣言はマネージ型または WinRT 型の定義内でのみ使用できます  
  
A[プロパティ](../../dotnet/how-to-use-properties-in-cpp-cli.md)またはマネージ Windows ランタイム内でのみ宣言可能型です。 ネイティブ型では、`property` キーワードがサポートされていません。  
  
## <a name="example"></a>例  
次の例では、C3813 を生成し、その修正方法を示しています。  
  
```cpp  
// C3813.cpp  
// compile by using: cl /c /clr C3813.cpp  
class A  
{  
   property int Int; // C3813  
};  
  
ref class B  
{  
   property int Int; // OK - declared within managed type  
};  
```
