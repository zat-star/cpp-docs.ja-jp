---
title: "コンパイラ エラー C2776 | Microsoft Docs"
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
  - "C2776"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2776"
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2776
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロパティごとに設定可能な 'get' メソッドは 1 つだけです。  
  
 [property](../../cpp/property-cpp.md) 拡張属性で指定できる `get` 関数は 1 つだけです。  このエラーは、複数の `get` 関数を指定した場合に発生します。  
  
 次の例では警告 C2776 が生成されます。  
  
```  
// C2776.cpp  
struct A {  
   __declspec(property(get=GetProp,get=GetPropToo))  
   // try the following line instead  
   // __declspec(property(get=GetProp))  
      int prop;   // C2776  
   int GetProp(void);  
   int GetPropToo(void);  
};  
```