---
title: "CL のコマンド ファイル | Microsoft Docs"
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
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe コンパイラ, コマンド ファイル"
  - "コマンド ファイル"
  - "コマンド ファイル, CL コンパイラ"
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CL のコマンド ファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンド ファイルは、オプションとファイル名を格納するテキスト ファイルです。このファイル内のオプションは、[コマンド ライン](../../build/reference/compiler-command-line-syntax.md)または[環境変数 CL](../../build/reference/cl-environment-variables.md) で指定したオプションと同じように処理されます。  コマンド ファイルは、環境変数 CL またはコマンド ラインで引数として指定できます。  コマンド ラインまたは環境変数 CL ではオプションとファイル名を 1 行しか指定できませんが、コマンド ファイルでは複数行指定できます。  
  
 コマンド ファイル内のオプションとファイル名が処理される順序は、そのコマンド ファイルの名前が環境変数 CL 内またはコマンド ライン上のどこにあるかによって異なります。  ただし、コマンド ファイル内に \/link オプションを指定すると、コマンド ファイル内の同じ行にある残りのすべてのオプションがリンカーに渡されます。  コマンド ファイル内の後続行にあるオプションと、コマンド ファイルを呼び出した地点より後ろにあるコマンド ライン オプションは、コンパイラ オプションとして処理されます。  オプションの指定順序については、「[CL オプションの指定順序](../../build/reference/order-of-cl-options.md)」を参照してください。  
  
 コマンド ファイルには CL の起動コマンドそのものは記述できません。  各オプションは 1 行で記述する必要があります。円記号 \(\\\) を使っても、単一のオプションを複数行に記述できません。  
  
 コマンド ファイルを指定するときは、ファイル名の先頭にアット マーク \(@\) を付けます。ファイル名には、絶対パスも相対パスも指定できます。  
  
 たとえば、RESP というコマンド ファイルに、次のコマンドが指定されていたとします。  
  
```  
/Og /link LIBC.LIB  
```  
  
 次に、次の CL コマンドを指定したとします。  
  
```  
CL /Ob2 @RESP MYAPP.C  
```  
  
 CL の起動コマンドに続くオプションは、次のように展開されます。  
  
```  
CL /Ob2 /Og MYAPP.C /link LIBC.LIB  
```  
  
 コマンド ラインに指定したオプションとコマンド ファイル内のオプションが効果的に組み合わされています。  
  
## 参照  
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)