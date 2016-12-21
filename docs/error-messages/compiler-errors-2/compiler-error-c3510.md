---
title: "コンパイラ エラー C3510 | Microsoft Docs"
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
  - "C3510"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3510"
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3510
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

依存する型ライブラリ 'type\_lib'  
  
 [no\_registry](../Topic/no_registry.md) および [auto\_search](../../preprocessor/auto-search.md) が `#import` に渡されましたが、コンパイラは参照タイプ ライブラリを検出できませんでした。  
  
 このエラーを解決するには、コンパイラですべてのタイプ ライブラリおよび参照タイプ ライブラリを利用できることを確認します。  
  
 次の例では警告 C3510 が生成されます。  
  
 以下の 2 つのタイプ ライブラリが構築され、C3510a.tlb が削除されたか、パスに存在しないとします。  
  
```  
// C3510a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C3510aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C3510  
   {  
      one, two, three  
   };  
};  
```  
  
 以下は、2 つ目のタイプ ライブラリのソース コードです。  
  
```  
// C3510b.idl  
// post-build command: del /f C3510a.tlb  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
library C3510bLib  
{  
   importlib ("C3510a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
   struct S_C3510 {  
      enum E_C3510 e;  
   };  
};  
```  
  
 以下は、クライアント コードです。  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```