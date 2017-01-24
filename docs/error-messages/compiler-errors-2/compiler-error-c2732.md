---
title: "コンパイラ エラー C2732 | Microsoft Docs"
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
  - "C2732"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2732"
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2732
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リンケージ指定は、別の 'function' に対する指定と矛盾しています。  
  
 関数は、別のリンケージ指定子で既に宣言されています。  
  
 このエラーは、インクルード ファイルに含まれるリンケージ指定子が異なることが原因で発生する可能性があります。  
  
 このエラーを修正するには、`extern` ステートメントを変更してリンケージが一致するようにします。  具体的には、`extern "C"` ブロックの `#include` ディレクティブをラップしないでください。  
  
## 使用例  
 次の例では、C2732 エラーが生成されます。  
  
```  
// C2732.cpp  
extern void func( void );   // implicit C++ linkage  
extern "C" void func( void );   // C2732  
```