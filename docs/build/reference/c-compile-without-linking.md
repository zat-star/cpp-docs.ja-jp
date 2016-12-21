---
title: "/c (リンクを行わないコンパイル) | Microsoft Docs"
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
  - "/c"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/c コンパイラ オプション [C++]"
  - "c コンパイラ オプション [C++]"
  - "-c コンパイラ オプション [C++]"
  - "cl.exe コンパイラ, コンパイル (リンクなし)"
  - "抑制 (リンクを)"
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /c (リンクを行わないコンパイル)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK の自動呼び出しを抑止します。  
  
## 構文  
  
```  
/c  
```  
  
## 解説  
 **\/c** を指定してコンパイルすると、.obj ファイルだけが作成されます。  ビルドのリンク フェーズを実行するには、適切なファイルとオプションを指定して LINK を明示的に呼び出す必要があります。  
  
 開発環境で作成した内部プロジェクトには、既定で **\/c** オプションが使用されます。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
-   このオプションは、開発環境では使用できません。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   このコンパイラ オプションをコードから設定するには、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>」を参照してください。  
  
## 使用例  
 次のコマンド ラインでは、オブジェクト ファイル FIRST.obj と SECOND.obj が作成されます。  THIRD.obj ファイルは無視されます。  
  
```  
CL /c FIRST.C SECOND.C THIRD.OBJ  
```  
  
 実行可能ファイルを作成するには、LINK を呼び出す必要があります。  
  
```  
LINK firsti.obj second.obj third.obj /OUT:filename.exe  
```  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)