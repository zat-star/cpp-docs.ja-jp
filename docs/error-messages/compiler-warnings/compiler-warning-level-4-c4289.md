---
title: "コンパイラの警告 (レベル 4) C4289 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4289"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4289"
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 4) C4289
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張が使用されています : 'var' : for ループで宣言したループ コントロール変数が for ループ スコープの外側で使用されています。  
  
 [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) および **\/Zc:forScope\-** でコンパイルするときに、[for](../../cpp/for-statement-cpp.md) ループ内で宣言された変数が **for** ループのスコープの後で使用されました。  
  
 **\/Ze** を使用して **for** ループ内での標準的な動作を指定する方法については、「[\/Zc:forScope \(for ループのスコープの強制準拠\)](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)」を参照してください。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[Compiler Warnings That Are Off by Default](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
 次の例では警告 C4289 が生成されます。  
  
```  
// C4289.cpp  
// compile with: /W4 /Zc:forScope-  
#pragma warning(default:4289)  
int main() {  
   for (int i = 0 ; ; )   // C4289  
      break;  
   i++;  
}  
```