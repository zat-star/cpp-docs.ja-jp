---
title: "コンパイラ エラー C2458 | Microsoft Docs"
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
  - "C2458"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2458"
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2458
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : クラス、構造体、共用体、列挙型が宣言内で再定義されています。  
  
 クラス、構造体、共用体、または列挙体はそれ自体の宣言内で再定義されています。  
  
 次の例では警告 C2458 が生成されます。  
  
```  
// C2458.cpp  
class C {  
   enum i { C };   // C2458  
};  
```