---
title: "コンパイラ エラー C2854 | Microsoft Docs"
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
  - "C2854"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2854"
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2854
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma hdrstop に構文エラーがあります。  
  
 `#pragma hdrstop` に指定したファイル名が無効です。  プラグマの後ろにファイル名を指定する場合は、次に示すように、かっこと引用符で囲みます。  
  
 次の例では警告 C2854 が生成されます。  
  
```  
// C2854.cpp  
// compile with: /c  
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854  
// try the following line instead  
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )  
```