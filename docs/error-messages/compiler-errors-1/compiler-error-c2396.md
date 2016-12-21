---
title: "Compiler Error C2396 | Microsoft Docs"
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
  - "C2396"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2396"
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C2396
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'your\_type::operator'type'' : CLR または WinRT のユーザー定義された変換関数は無効です。変換元または変換先が次の値でなければなりません: 'T^'、'T^%'、'T^&' \(ここで T \= 'your\_type'\)  
  
 Windows ランタイム型またはマネージ型の変換関数に、変換関数が含まれる型と同じ型を持つ 1 つ以上のパラメーターがありません。  
  
 次の例では、C2396 を生成し、その修正方法を示しています。  
  
```  
// C2396.cpp  
// compile with: /clr /c  
  
ref struct Y {  
   static operator int(char c);   // C2396  
  
   // OK  
   static operator int(Y^ hY);  
   // or  
   static operator Y^(char c);  
};  
```