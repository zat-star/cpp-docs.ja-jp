---
title: "コンパイラ エラー C2017 | Microsoft Docs"
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
  - "C2017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2017"
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エスケープ シーケンスの使い方が正しくありません。  
  
 \\t などのエスケープ シーケンスが、文字定数または文字列定数の外側にあります。  
  
 次の例では警告 C2017 が生成されます。  
  
```  
// C2017.cpp  
int main() {  
   char test1='a'\n;   // C2017  
   char test2='a\n';   // ok  
}  
```  
  
 C2017 警告は、文字列化演算子の文字列にエスケープ シーケンスが含まれている場合に発生します。  
  
 次の例では警告 C2017 が生成されます。  
  
```  
// C2017b.cpp  
#define TestDfn(x) AfxMessageBox(#x)  
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017  
```