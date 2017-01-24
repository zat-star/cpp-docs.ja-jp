---
title: "リンカ ツール エラー LNK2011 | Microsoft Docs"
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
  - "LNK2011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2011"
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK2011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プリコンパイル済みオブジェクトはリンクされていません。イメージは動作しない可能性があります。  
  
 プリコンパイル済みヘッダーを使用するときには、プリコンパイル済みヘッダーと同時に作成したファイルもリンクする必要があります。  他のソース ファイルで使うためのプリコンパイル済みヘッダーを作る時に使用したソース ファイルがあるときには、オブジェクト ファイルも含めてください。  
  
 たとえば、STUB.cpp というファイルをコンパイルして、ほかのソース ファイル用にプリコンパイル済みヘッダーを作ったときは、STUB.obj も一緒にリンクする必要があります。そうしないと、このエラーが発生します。  以下の例では、第 1 行でプリコンパイル済みヘッダー COMMON.pch を作成しています。このファイルは第 2 行と第 3 行で PROG1.cpp と PROG2.cpp と共に使用されます。  STUB.cpp には、PROG1.cpp および PROG2.cpp と同じ `#include` 行だけがあり、プリコンパイル済みヘッダーを作成するためだけに使用されます。  最後の行では、STUB.obj もリンクする必要があります。STUB.obj を指定しないと、LNK2011 が発生します。  
  
```  
cl /c /Yccommon.h stub.cpp  
cl /c /Yucommon.h prog1.cpp  
cl /c /Yucommon.h prog2.cpp  
link /out:prog.exe stub.obj prog1.obj prog2.obj  
```