---
title: "コンパイラ エラー C2976 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2976"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2976"
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2976
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'識別子' : 型引数が少なすぎます。  
  
 ジェネリックまたはテンプレートに与えられた実引数が足りません。  ジェネリック宣言またはテンプレート宣言を調べて、パラメーターの正しい数を確認してください。  
  
 このエラーは、STL コンポーネントのテンプレート引数が足りないことが原因で発生する場合があります。  
  
 次の例では警告 C2976 が生成されます。  
  
```  
// C2976.cpp  
template <class T>   
struct TC {  
   T t;  
};  
int main() {  
   TC<>* t;   // C2976  
   TC<int>* t2;   // OK  
}  
```  
  
 C2976 は、ジェネリックを使用しているときも発生します。  
  
```  
// C2976b.cpp  
// compile with: /clr  
generic <class T>  
ref struct GC {  
   T t;  
};  
  
int main() {  
   GC<>^ g;   // C2976  
   GC<int>^ g2;   // OK  
}  
```