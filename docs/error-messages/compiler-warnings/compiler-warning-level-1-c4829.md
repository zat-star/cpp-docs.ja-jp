---
title: "コンパイラの警告 (レベル 1) C4829 | Microsoft Docs"
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
  - "C4829"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4829"
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4829
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数 main への正しくないパラメーターである可能性があります。'int main\(Platform::Array\<Platform::String^\>^ argv\)' を使用してください  
  
 main などの特定の関数は、参照型のパラメーターを受け取れません。  コンパイルは成功しても、結果のイメージは実行できない場合があります。  
  
 次の例では C4829 が生成されます。  
  
```  
// C4829.cpp  
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp  
int main(Platform::String ^ s) {}   // C4829  
  
```