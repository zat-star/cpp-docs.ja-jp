---
title: "コンパイラ エラー C2569 | Microsoft Docs"
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
  - "C2569"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2569"
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2569
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'EnumOrUnion' : 共用体からクラスが派生しています。  
  
 指定された共用体または列挙型から型を派生する必要がある場合は、その共用体または列挙型をクラスあるいは構造体に変更してください。  
  
 次の例では警告 C2569 が生成されます。  
  
```  
// C2569.cpp  
// compile with: /c  
union ubase {};  
class cHasPubUBase : public ubase {};   // C2569  
// OK  
struct sbase {};  
class cHasPubUBase : public sbase {};  
```