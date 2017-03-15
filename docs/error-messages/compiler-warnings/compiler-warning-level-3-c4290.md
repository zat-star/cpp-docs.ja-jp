---
title: "コンパイラの警告 (レベル 3) C4290 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4290"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4290"
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラの警告 (レベル 3) C4290
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+ の例外の指定は無視されます。関数が \_\_declspec\(nothrow\) でないことのみ表示されます。  
  
 関数が例外指定を使用して宣言されています。これは Visual C\+\+ で認識されますが、実装されません。  コンパイル中に無視された例外指定を持つコードは、例外指定をサポートする将来のバージョンでは、再コンパイルとリンクを行ってから再利用する必要があります。  
  
 詳細については、「[例外の仕様 \(スロー\)](../../cpp/exception-specifications-throw-cpp.md)」を参照してください。  
  
 [warning](../../preprocessor/warning.md) プラグマを使用すると、この警告を回避できます。  
  
```  
#pragma warning( disable : 4290 )  
```  
  
 次の例では、C4290 警告が生成されます。  
  
```  
// C4290.cpp  
// compile with: /EHs /W3 /c  
void f1(void) throw(int) {}   // C4290  
  
// OK  
void f2(void) throw() {}  
void f3(void) throw(...) {}  
```