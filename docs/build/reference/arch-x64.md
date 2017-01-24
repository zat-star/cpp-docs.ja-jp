---
title: "/arch (x64) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /arch (x64)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

x64 でのコード生成のアーキテクチャを指定します。  「[\/arch \(x86\)](../../build/reference/arch-x86.md)」および「[\/arch \(ARM\)](../../build/reference/arch-arm.md)」を参照してください。  
  
## 構文  
  
```  
/arch:[AVX|AVX2]  
```  
  
## 引数  
 **\/arch:AVX**  
 Advanced Vector Extensions 命令の使用を有効にします。  
  
 **\/arch:AVX2**  
 Advanced Vector Extensions 2 命令の使用を有効にします。  
  
## 解説  
 **\/arch** はネイティブ関数のコード生成にのみ影響します。  [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) を指定してコンパイルした場合、**\/arch** はマネージ関数のコード生成に影響しません。  
  
 `__AVX__` プリプロセッサ シンボルは、**\/arch:AVX** コンパイラ オプションを指定するときに定義します。  `__AVX2__` プリプロセッサ シンボルは、**\/arch:AVX2** コンパイラ オプションを指定するときに定義します。  詳細については、「[定義済みマクロ](../../preprocessor/predefined-macros.md)」を参照してください。  **\/arch:AVX2** オプションは、Visual Studio 2013 更新プログラム 2、バージョン 12.0.34567.1 で導入されました。  
  
### \/arch:AVX または \/arch:AVX2 コンパイラ オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]**、**\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コード生成\]** プロパティ ページを選択します。  
  
4.  **\[拡張命令セットを有効にする\]** ドロップダウン ボックスで、**\[Advanced Vector Extensions \(\/arch:AVX\)\]** または **\[Advanced Vector Extensions 2 \(\/arch:AVX2\)\]** を選択します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>」を参照してください。  
  
## 参照  
 [\/arch \(最小限の CPU アーキテクチャ\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)