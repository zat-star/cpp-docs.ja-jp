---
title: "コンパイラ エラー C3816 | Microsoft Docs"
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
  - "C3816"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3816"
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3816
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration' は、異なるマネージ修飾子または WinRT 修飾子を伴って、以前に宣言または定義されていました  
  
 事前宣言および実際の宣言では、属性の宣言に競合や不整合がないことが求められます。  
  
 次の例では、C3816 を生成し、その修正方法を示しています。  
  
```  
// C3816a.cpp  
// compile with: /clr /c  
class C1;  
// try the following line instead  
// ref class C1;  
  
ref class C1{  // C3816, forward declaration does not use ref  
};  
```