---
title: "コンパイラ エラー C2743 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2743"
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : \_\_clrcall デストラクターまたはコピー コンストラクターを伴うネイティブをキャッチすることはできません  
  
 **\/clr:pure** ではなく **\/clr** を指定してコンパイルされたモジュールでネイティブ型の例外をキャッチしようとしましたが、その型のデストラクターまたはコピー コンストラクターで \_`_clrcall` 呼び出し規約を使用しています。  
  
 **\/clr:pure** ではなく **\/clr** を指定してコンパイルした場合、例外処理はネイティブ型のメンバー関数が [\_\_clrcall](../../cpp/clrcall.md) ではなく [\_\_cdecl](../Topic/__cdecl.md) になることを要求します。  `__clrcall` 呼び出し規約を使用するメンバー関数を持つネイティブ型は、**\/clr** を指定してコンパイルされたモジュール内でキャッチできません。  
  
 詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
## 使用例  
 次の例では C2743 エラーが生成されます。  
  
```  
// C2743.cpp  
// compile with: /clr  
public struct S {  
   __clrcall ~S() {}  
};  
  
public struct T {  
   ~T() {}  
};  
  
int main() {  
   try {}  
   catch(S) {}   // C2743  
   // try the following line instead  
   // catch(T) {}  
  
   try {}  
   catch(S*) {}   // OK  
}  
```