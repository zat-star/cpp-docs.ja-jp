---
title: "コンパイラ COM のグローバル関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe コンパイラ, COM サポート"
  - "COM, コンパイラ サポート"
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コンパイラ COM のグローバル関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 使用できるルーチンは次のとおりです。  
  
|関数|説明|  
|--------|--------|  
|[\_com\_raise\_error](../cpp/com-raise-error.md)|失敗に応答して [\_com\_error](../cpp/com-error-class.md) をスローします。|  
|[\_set\_com\_error\_handler](../cpp/set-com-error-handler.md)|COM のエラー処理に使用する既定の関数を置き換えます。|  
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|`BSTR` 値を **char \*** に変換します。|  
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|**char \*** 値を `BSTR` に変換します。|  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)   
 [コンパイラ COM サポート](../Topic/Compiler%20COM%20Support.md)