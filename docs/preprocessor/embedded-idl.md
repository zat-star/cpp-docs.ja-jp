---
title: "embedded_idl | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "embedded_idl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "embedded_idl 属性"
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# embedded_idl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 属性が生成されたコードを保持して、タイプ ライブラリを .tlh ファイルに書き込むことを指定します。  
  
## 構文  
  
```  
embedded_idl[("param")]  
```  
  
#### パラメーター  
 `param`  
 次の 2 つの値のいずれかを指定します。  
  
-   emitidl: typelib からインポートされた情報は、属性付きプロジェクト用に生成された IDL に存在します。  これは既定値であり、`embedded_idl` にパラメーターを指定しない場合に有効になります。  
  
-   no\_emitidl: typelib からインポートされた型情報が、属性付きプロジェクト用に生成された IDL に存在しません。  
  
## 使用例  
  
```  
// import_embedded_idl.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib2")];  
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")  
```  
  
## 解説  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)