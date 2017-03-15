---
title: "コンパイラ エラー C2755 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2755"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2755"
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2755
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param' : 部分的特殊化の非型テンプレート パラメーターは、単純な識別子でなければなりません。  
  
 非型パラメーターは、コンパイル時にコンパイラが単一の識別子または定数値に解決できる単純な識別子にする必要があります。  
  
 次の例では警告 C2755 が生成されます。  
  
```  
// C2755.cpp  
template<int I, int J>  
struct A {};  
  
template<int I>   
struct A<I,I*5> {};   // C2755  
// try the following line instead  
// struct A<I,5> {};  
```