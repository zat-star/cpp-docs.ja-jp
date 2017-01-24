---
title: "コンパイラ エラー C3828 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3828"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3828"
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3828
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'object type': マネージ クラスまたは WinRT クラスのインスタンス作成時に仮引数を使用することはできません  
  
 マネージ型または Windows ランタイム型のオブジェクトの作成時に、仮引数付きの演算子 [ref new, gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md) または [new](../../cpp/new-operator-cpp.md) を使用することはできません。  
  
 次の例では、C3828 を生成し、その修正方法を示しています。  
  
```  
// C3828a.cpp  
// compile with: /clr  
ref struct M {  
};  
  
ref struct N {  
   static array<char>^ bytes = gcnew array<char>(256);  
};  
  
int main() {  
   M ^m1 = new (&N::bytes) M();   // C3828  
   // The following line fixes the error.  
   // M ^m1 = gcnew M();  
}  
```