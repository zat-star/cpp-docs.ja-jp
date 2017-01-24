---
title: "/DELAYLOAD (遅延読み込みのインポート) | Microsoft Docs"
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
  - "/delayload"
  - "VC.Project.VCLinkerTool.DelayLoadDLLS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAYLOAD リンカー オプション"
  - "遅延読み込み (DLL を), /DELAYLOAD オプション"
  - "DELAYLOAD リンカー オプション"
  - "-DELAYLOAD リンカー オプション"
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DELAYLOAD (遅延読み込みのインポート)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAYLOAD:dllname  
  
```  
  
## パラメーター  
 `dllname`  
 遅延読み込みする DLL の名前。  
  
## 解説  
 \/DELAYLOAD オプションを指定すると、`dllname` で指定された DLL は、その DLL 内の関数に対するプログラムの最初の呼び出しが行われたときのみ読み込まれます。  詳細については、「[リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)」を参照してください。  このオプションは、選択した DLL を指定するのに必要なだけ繰り返して使用できます。  プログラムを Delayimp.lib にリンクする場合は、Delayimp.lib を使用する必要があります。または、独自の遅延読み込みヘルパー関数を実装することもできます。  
  
 [\/DELAY](../../build/reference/delay-delay-load-import-settings.md) オプションは、遅延読み込みされる各 DLL のバインド オプションと読み込みオプションを指定します。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーで、**\[入力\]** のプロパティ ページをクリックします。  
  
3.  \[DLL の遅延読み込み\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)