---
title: "コンパイラ エラー C3412 | Microsoft Docs"
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
  - "C3412"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3412"
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3412
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'template' : 現在のスコープでテンプレートを特殊化できません。  
  
 テンプレートが特化できるのは、グローバル スコープまたは名前空間スコープの中だけです。クラス スコープでは特化できません。  
  
## 使用例  
 次の例では C3412 エラーが生成されます。  
  
```  
// C3412.cpp  
template <class T>  
struct S {  
   template <>  
   struct S<int> {};   // C3412 in a class  
};  
```  
  
## 使用例  
 解決方法の例を次に示します。  
  
```  
// C3412b.cpp  
// compile with: /c  
template <class T>  
struct S {};  
  
template <>  
struct S<int> {};  
```