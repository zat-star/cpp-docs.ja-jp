---
title: "コンパイラの警告 (レベル 1 および 4) C4112 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4112"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4112"
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1 および 4) C4112
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#line は 1 から number の整数を必要とします。  
  
 許可された範囲を超えた整数パラメーターが [\#line](../Topic/%23line%20Directive%20\(C-C++\).md) ディレクティブに指定されています。  
  
 指定したパラメーターが 1 より小さい場合、行カウンターは 1 にリセットされます。 指定したパラメーターが、コンパイラで定義された制限値である *number* より大きい場合、行カウンターは変更されません。 これは、ANSI 互換オプション \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) ではレベル 1 の警告であり、Microsoft 拡張機能オプション \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\) ではレベル 4 の警告です。  
  
 次の例では C4112 が生成されます。  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```