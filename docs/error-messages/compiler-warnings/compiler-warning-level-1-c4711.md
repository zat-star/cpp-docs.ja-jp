---
title: "コンパイラの警告 (レベル 1) C4711 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4711"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4711"
ms.assetid: 270506ab-fead-4328-b714-2978113be238
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4711
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数 'function' にインライン展開を選択しました。  
  
 インライン展開の指定はありませんが、コンパイラは指定された関数をインライン展開しました。  
  
 [\/Ob2](../../build/reference/ob-inline-function-expansion.md) を指定すると、C4711 エラーが有効になります。  
  
 インライン展開はコンパイラの判断によって行われます。  この警告は、情報を提供するためだけのものです。  
  
 既定では、この警告はオフに設定されています。  警告を有効にするには、[\#pragma warning](../../preprocessor/warning.md) を使用します。  詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。