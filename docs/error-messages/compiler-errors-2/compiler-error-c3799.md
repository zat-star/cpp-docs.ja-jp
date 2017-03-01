---
title: "コンパイラ エラー C3799 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3799
dev_langs:
- C++
helpviewer_keywords:
- C3799
ms.assetid: 336a2811-9370-4e6e-b03b-325bda470805
caps.latest.revision: 5
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
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: b38c1e2594b79d6643b0697f9b896a7e43f8a292
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3799"></a>コンパイラ エラー C3799
インデックス付きプロパティは空のパラメーター リストを含むことはできません  
  
インデックス付きプロパティの宣言が正しくありません。 詳細については、次を参照してください。[方法: プロパティを使用して C + で/cli CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)します。  
  
## <a name="example"></a>例  
次の例では、C3799 を生成し、それを修正する方法について説明します。  
  
```cpp  
// C3799.cpp  
// compile with: /clr /c  
ref struct C {  
   property int default[] {   // C3799  
   // try the following line instead  
   // property int default[int] {  
      int get(int index) { return 0; }  
      void set(int index, int value) {}  
   }  
};  
```
