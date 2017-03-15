---
title: "コンパイラの警告 (レベル 3) C4800 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4800"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4800"
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 3) C4800
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : ブール値を 'true' または 'false' に強制的に設定します \(警告の処理\)。  
  
 非 `bool` 値を `bool` 型に代入するか強制的に変換すると、この警告が生成されます。  このメッセージが表示される状況としては、値 **true** または **false** しか取らない `int` 変数を `bool` 変数に代入しており、`bool` 型として再宣言できる場合が含まれます。  `bool` 型を使用するように式を書き直すことができない場合は、式に "`!=0`" を追加して `bool` 型にできます。  式をただ `bool` 型にキャストしても、この警告が生成されます \(設計仕様\)。  
  
 次の例では警告 C4800 が生成されます。  
  
```  
// C4800.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
  
   // try..  
   // bool i = 0;  
  
   bool j = i;   // C4800  
   j++;  
}  
```