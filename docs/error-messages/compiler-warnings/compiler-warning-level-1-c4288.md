---
title: "コンパイラの警告 (レベル 1) C4288 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4288"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4288"
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4288
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張が使用されています : 'var' : for ループで宣言したループ コントロール変数が for ループ スコープの外側で使用されています。外側のスコープの宣言と競合しています。  
  
 [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) および **\/Zc:forscope\-** でコンパイルするときに、**for** ループ内で宣言された変数が [for](../../cpp/for-statement-cpp.md) ループのスコープの後で使用されました。  Microsoft C\+\+ の拡張機能では、この変数をスコープ内に残すことができます。警告 C4288 は、変数の最初の宣言が使用されていないことを示します。  
  
 \/Ze を使用して **for** ループ内での Microsoft 拡張機能を指定する方法については、「[\/Zc:forScope \(for ループのスコープの強制準拠\)](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)」を参照してください。  
  
 次の例では警告 C4288 が生成されます。  
  
```  
// C4288.cpp  
// compile with: /W1 /c /Zc:forScope-  
int main() {  
   int i = 0;    // not used in this program  
   for (int i = 0 ; ; ) ;  
   i++;   // C4288 using for-loop declaration of i  
}  
```