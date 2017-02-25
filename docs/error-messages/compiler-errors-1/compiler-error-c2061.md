---
title: "コンパイラ エラー C2061 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2061"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2061"
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# コンパイラ エラー C2061
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

構文エラー : 識別子 'identifier'  
  
 予期しない位置で identifier を見つけました。  `identifier` は、使用する前に宣言してください。  
  
 初期化子がかっこで囲まれている可能性があります。  このエラーを回避するには、宣言子をかっこで囲むか、宣言子を `typedef` にしてください。  
  
 このエラーは、コンパイラがクラス テンプレート引数として式を検出した場合にも発生することがあります。[typename](../Topic/typename.md) を使用して、それが型であることをコンパイラに通知してください。  
  
 次の例では警告 C2061 が生成されます。  
  
```  
// C2061.cpp  
// compile with: /c  
template < A a >   // C2061  
// try the following line instead  
// template < typename b >  
class c{};  
```  
  
 C2061 は、インスタンス名を [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) に渡す場合に発生することがあります。  
  
```  
// C2061b.cpp  
// compile with: /clr  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   System::Type ^ pType = typeid<pG>;   // C2061  
   System::Type ^ pType2 = typeid<G>;   // OK  
}  
```