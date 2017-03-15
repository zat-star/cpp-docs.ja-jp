---
title: "リンカ ツール エラー LNK2033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2033"
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# リンカ ツール エラー LNK2033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

未解決の typeref トークン \('トークン'\) \('型'\) です。  
  
 MSIL メタデータに型の定義がありません。  
  
 LNK2033 は、**\/clr:safe** を指定してコンパイルするときに MSIL モジュールには型の事前宣言があるだけという状況で、MSIL モジュールで型が参照されると発生することがあります。  
  
 型は、**\/clr:safe** で定義する必要があります。  
  
 詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
## 使用例  
 次の例では LNK2033 エラーが生成されます。  
  
```  
// LNK2033.cpp  
// compile with: /clr:safe  
// LNK2033 expected  
ref class A;  
ref class B {};  
  
int main() {  
   A ^ aa = nullptr;  
   B ^ bb = nullptr;   // OK  
};  
```