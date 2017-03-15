---
title: "コンパイラの警告 (レベル 1) C4772 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4772"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4772"
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラの警告 (レベル 1) C4772
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#import は存在しない型ライブラリから型を参照しました。 'missing\_type' はプレースホルダーとして使用されます  
  
 タイプ ライブラリが [\#import](../Topic/%23import%20Directive%20\(C++\).md) ディレクティブで参照されました。  一方、タイプ ライブラリには、`#import` で参照されていない別のタイプ ライブラリへの参照が含まれていました。  この別の .tlb ファイルが見つかりませんでした。  
  
 [\/I \(追加インクルード ディレクトリ\)](../../build/reference/i-additional-include-directories.md) コンパイラ オプションを使用して別のディレクトリを指定している場合、コンパイラはこれらのディレクトリからタイプ ライブラリを見つけることができません。  コンパイラが別のディレクトリからタイプ ライブラリを見つけられるようにするためには、これらのディレクトリを PATH 環境変数に追加する必要があります。  
  
 この警告は、既定ではエラーとして発行されます。  C4772 は、\/W0 では抑止できません。  
  
## 使用例  
 これは、C4772 の再現に必要な 1 つ目のタイプ ライブラリです。  
  
```  
// c4772a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C4772aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c100")]  
   enum E_C4772a  
   {  
      one, two, three  
   };  
};  
```  
  
## 使用例  
 これは、C4772 の再現に必要な 2 つ目のタイプ ライブラリです。  
  
```  
// c4772b.idl  
// post-build command: del /f C4772a.tlb  
// C4772a.tlb is available when c4772b.tlb is built  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
library C4772bLib  
{  
   importlib ("c4772a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
   struct S_C4772b  
   {  
      enum E_C4772a e;  
   };  
};  
```  
  
## 使用例  
 次の例では警告 C4772 が生成されます。  
  
```  
// C4772.cpp  
// assumes that C4772a.tlb is not available to the compiler  
// #import "C4772a.tlb"  
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve  
                       // and make sure c4772a.tlb is on disk  
```