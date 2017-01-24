---
title: "コンパイラ エラー C2688 | Microsoft Docs"
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
  - "C2688"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2688"
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2688
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'C2::fgrv' : covariant は varargs 関数でサポートされていない複数の、または仮想継承を返します。  
  
 Visual C\+\+ では、関数に可変個の引数が含まれている場合、**Covariant** 型の戻り値はサポートされません。  
  
 このエラーを解決するには、可変個の引数を使用しないように関数を定義するか、またはすべての仮想関数の戻り型を同じにします。  
  
 次の例では警告 C2688 が生成されます。  
  
```  
// C2688.cpp  
struct G1 {};  
struct G2 {};  
struct G3 : G1, G2 {};  
struct G4 {};  
struct G5 {};  
struct G6 : G4, G5 {};  
struct G7 : G3, G6 {};  
  
struct C1 {  
   virtual G4& fgrv(int,...);  
};  
  
struct C2 : C1 {  
   virtual G7& fgrv(int,...);   // C2688, does not return G4&  
};  
```