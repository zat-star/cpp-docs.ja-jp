---
title: "@ (コンパイラ応答ファイルの指定) | Microsoft Docs"
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
  - "@"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "@ コンパイラ オプション"
  - "cl.exe コンパイラ, 指定 (応答ファイルを)"
  - "応答ファイル, C/C++ コンパイラ"
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# @ (コンパイラ応答ファイルの指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラ応答ファイルを指定します。  
  
## 構文  
  
```  
@response_file  
```  
  
## Arguments  
 `response_file`  
 コンパイラ コマンドが記述されたテキスト ファイル。  
  
## 解説  
 応答ファイルには、コマンド ラインで指定するあらゆるコマンドを記述できます。  これは、コマンド ライン引数が 127 文字を超える場合に便利です。  
  
 **@** オプションは、応答ファイル内では指定できません。  つまり、応答ファイルの中に別の応答ファイルを埋め込むことはできません。  
  
 コマンド ラインから、`@respfile.1 @respfile.2` のように、応答ファイル オプションをいくつでも指定できます。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
-   応答ファイルは、コマンド ラインで指定する必要があります。開発環境では指定できません。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   このコンパイラ オプションは、コードからは変更できません。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)