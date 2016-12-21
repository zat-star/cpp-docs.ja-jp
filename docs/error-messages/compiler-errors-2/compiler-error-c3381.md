---
title: "コンパイラ エラー C3381 | Microsoft Docs"
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
  - "C3381"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3381"
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3381
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'アセンブリ' : アセンブリ アクセス指定子は、\/clr オプションと共にコンパイルされたコードでのみ使用できます  
  
 ネイティブな型は、アセンブリ外でも参照できますが、ネイティブな型のアセンブリ アクセスは、**\/clr** コンパイル単位でのみ指定できます。  
  
 詳細については、「[型の可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)」と「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
## 使用例  
 次の例では C3381 エラーが生成されます。  
  
```  
// C3381.cpp  
// compile with: /c  
public class A {};   // C3381  
```