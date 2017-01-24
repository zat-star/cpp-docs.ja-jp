---
title: "/Fi (出力ファイル名のプリプロセス) | Microsoft Docs"
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
  - "/Fi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fi コンパイラ オプション (C++)"
  - "Fi コンパイラ オプション (C++)"
  - "-Fi コンパイラ オプション (C++)"
  - "プリプロセス (出力ファイルを), ファイル名"
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fi (出力ファイル名のプリプロセス)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/P \(プリプロセス出力のファイルへの書き込み\)](../../build/reference/p-preprocess-to-a-file.md) コンパイラ オプションのプリプロセス済み出力の書き込み先となる出力ファイルの名前を指定します。  
  
## 構文  
  
```  
/Fipathname  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`pathname`|**\/P** コンパイラ オプションによって生成される出力ファイルの名前とパス。|  
  
## 解説  
 **\/Fi** コンパイラ オプションは、**\/P** コンパイラ オプションと組み合わせて使用します。  
  
 `pathname` パラメーターにパスのみを指定した場合、プリプロセス済みの出力ファイルの基本名として、ソース ファイルの基本名が使用されます。  `pathname` パラメーターには、特定のファイル名拡張子は必要ありません。  ただし、ファイル名拡張子を指定しない場合は、".i" という拡張子が使用されます。  
  
## 使用例  
 次のコマンド ラインでは、PROGRAM.cpp をプリプロセスし、コメントを保持し、[\#line](../Topic/%23line%20Directive%20\(C-C++\).md) ディレクティブを挿入し、結果を MYPROCESS.i というファイルに書き込みます。  
  
```  
CL /P /FiMYPROCESS.I PROGRAM.CPP  
```  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [\/P \(プリプロセス出力のファイルへの書き込み\)](../../build/reference/p-preprocess-to-a-file.md)   
 [パス名の指定](../Topic/Specifying%20the%20Pathname.md)