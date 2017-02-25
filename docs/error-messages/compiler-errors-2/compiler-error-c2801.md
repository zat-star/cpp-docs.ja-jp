---
title: "コンパイラ エラー C2801 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2801"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2801"
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2801
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator' はスタティックでないメンバーでなければなりません  
  
 以下の演算子は、非静的メンバーとして宣言したときだけオーバーロードできます。  
  
-   代入演算子 `=`  
  
-   クラス メンバーに対するアクセス演算子 `->`  
  
-   添字演算子 `[]`  
  
-   関数呼び出し演算子 `()`  
  
 C2801 の原因 :  
  
-   オーバーロードされた演算子は、クラス、構造体、共用体のいずれのメンバーでもありません。  
  
-   オーバーロードされた演算子は `static` として宣言されています。  
  
-   次の例では警告 C2801 が生成されます。  
  
```  
// C2801.cpp  
// compile with: /c  
operator[]();   // C2801 not a member  
class A {  
   static operator->();   // C2801 static  
   operator()();   // OK  
};  
```