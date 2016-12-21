---
title: "コンパイラの警告 (レベル 4) C4571 | Microsoft Docs"
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
  - "C4571"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4571"
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4571
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

情報: catch\(...\) の意味が Visual C\+\+ 7.1 から変更されています。構造化例外 \(SEH\) はキャッチされません。  
  
 C4571 は **\/EHs** でのコンパイル時にすべての catch\(...\) ブロックに対して生成されます。  
  
 **\/EHs** でのコンパイル時に、catch\(...\) ブロックは構造化例外 \(0 による除算や null ポインターなど\) をキャッチしません。catch\(...\) ブロックは明示的にスローされた C\+\+ 例外だけをキャッチします。詳細については、「[例外処理](../../cpp/exception-handling-in-visual-cpp.md)」を参照してください。  
  
 既定では、この警告はオフに設定されています。**\/EHs** でのコンパイル時に catch \(...\) ブロックが構造化例外をキャッチしないようにするには、この警告をオンにします。詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
 C4571 は、次のいずれかの方法で解決します。  
  
-   catch\(...\) ブロックで構造化例外をキャッチする場合は、**\/EHa** でコンパイルします。  
  
-   catch\(...\) ブロックを使用し、ただし構造化例外をキャッチしない場合は、C4571 を有効にしないでください。構造化例外は、構造化例外処理キーワード \(**\_\_try**、**\_\_except**、および **\_\_finally**\) を使用してキャッチできます。ただし、コンパイルされた **\/EHs** デストラクターが呼び出されるのは C\+\+ 例外がスローされたときだけで、SEH 例外の発生時には呼び出されません。  
  
-   catch\(...\) ブロックを特定の C\+\+ 例外の catch ブロックに置き換え、オプションで C\+\+ 例外処理 \(**\_\_try**、**\_\_except**、および **\_\_finally**\) について構造化例外処理を追加します。詳細については、「[構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md)」を参照してください。  
  
 詳細については、「[\/EH \(例外処理モデル\)](../../build/reference/eh-exception-handling-model.md)」を参照してください。  
  
## 使用例  
 次の例では C4571 エラーが生成されます。  
  
```  
// C4571.cpp  
// compile with: /EHs /W4 /c  
#pragma warning(default : 4571)  
int main() {  
   try {  
      int i = 0, j = 1;  
      j /= i;   // this will throw a SE (divide by zero)  
   }  
   catch(...) {}   // C4571 warning  
}  
```