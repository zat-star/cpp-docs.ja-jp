---
title: "コンパイラ エラー C2813 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2813"
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2813
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#import は \/MP でサポートされていません  
  
 C2813 は、コンパイラのコマンドで **\/MP** コンパイラ オプションとコンパイルする 2 つ以上のファイルを指定し、1 つ以上のファイルに [\#import](../Topic/%23import%20Directive%20\(C++\).md) プリプロセッサ ディレクティブが含まれている場合に生成されます。[\#Import](../Topic/%23import%20Directive%20\(C++\).md) ディレクティブによって、指定したタイプ ライブラリ内の型から C\+\+ クラスが生成され、これらのクラスが 2 つのヘッダー ファイルに書き込まれます。 複数のコンパイル単位で同じタイプ ライブラリがインポートされる場合、それらの単位は同時に同じヘッダー ファイルに書き込もうとすると競合するため、[\#Import](../Topic/%23import%20Directive%20\(C++\).md) ディレクティブはサポートされていません。  
  
 このコンパイラ エラーと **\/MP** コンパイラ オプションは、[!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] の新機能です。  
  
## 使用例  
 次の例では C2813 が生成されます。 "compile with:" コメントのコマンド ラインは、**\/MP** および **\/c** コンパイラ オプションを使用して複数のファイルをコンパイルすることをコンパイラに示します。 少なくとも 1 つのファイルに [\#import](../Topic/%23import%20Directive%20\(C++\).md) ディレクティブが含まれています。 この例のテストのために、同じファイルを 2 回使用します。  
  
```  
// C2813.cpp // compile with: /MP /c C2813.cpp C2813.cpp #import "C:\windows\system32\stdole2.tlb"   // C2813 int main() { }  
```