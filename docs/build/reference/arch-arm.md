---
title: "/arch (ARM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# /arch (ARM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ARM でのコード生成のアーキテクチャを指定します。  [\/arch \(x86\)](../../build/reference/arch-x86.md) および [\/arch \(x64\)](../../build/reference/arch-x64.md) も参照してください。  
  
## 構文  
  
```  
/arch:[ARMv7VE|VFPv4]  
```  
  
## 引数  
 **\/arch:ARMv7VE**  
 ARMv7VE 仮想化拡張命令の使用を有効にします。  
  
 **\/arch:VFPv4**  
 ARM VFPv4 命令の使用を有効にします。  このオプションを指定しない場合は、VFPv3 が既定値です。  
  
## 解説  
 `_M_ARM_FP` マクロ \(ARM のみ\) は、**\/arch** コンパイラ オプションが使用された場合にどれが使用されたかを示します。  詳細については、「[定義済みマクロ](../../preprocessor/predefined-macros.md)」を参照してください。  
  
 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) を指定してコンパイルした場合、**\/arch** はマネージ関数のコード生成に影響しません。  **\/arch** はネイティブ関数のコード生成にのみ影響します。  
  
### Visual Studio で、\/arch:ARMv7VE または\/arch:VFPv4 コンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\[追加のオプション\]** ボックスに、「`/arch:ARMv7VE`」または「`/arch:VFPv4`」を追加します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>」を参照してください。  
  
## 参照  
 [\/arch \(最小限の CPU アーキテクチャ\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)