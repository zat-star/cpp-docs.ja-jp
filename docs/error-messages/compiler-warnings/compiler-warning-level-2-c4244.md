---
title: "コンパイラの警告 (レベル 2) C4244 | Microsoft Docs"
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
  - "C4244"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4244"
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 2) C4244
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'引数' : 'type1' から 'type2' への変換です。データが失われる可能性があります。  
  
 浮動小数点型が整数型に変換されました。データが失われた可能性があります。  
  
 C4244 が発生した場合は、互換性のある型を使用するようにプログラムを変更するか、別の論理をコードに追加するかして、変換される値の範囲が使用する型と常に互換性があるようにします。  
  
 C4244 は、レベル 3 およびレベル 4 で発生する可能性もあります。詳細については、「[コンパイラの警告 \(レベルs 3 and 4\) C4244](../Topic/Compiler%20Warning%20\(levels%203%20and%204\)%20C4244.md)」を参照してください。  
  
## 使用例  
 次の例では警告 C4244 が生成されます。  
  
```  
// C4244_level2.cpp  
// compile with: /W2  
  
int f(int x){ return 0; }  
int main() {  
   double x = 10.1;  
   int i = 10;  
   return (f(x));   // C4244  
   // try the following line instead  
   // return (f(i));  
}  
```