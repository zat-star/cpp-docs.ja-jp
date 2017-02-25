---
title: "/KEYCONTAINER (アセンブリに署名するためのキー コンテナーの指定) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.KeyContainer"
  - "/keycontainer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/KEYCONTAINER リンカー オプション"
  - "KEYCONTAINER リンカー オプション"
  - "-KEYCONTAINER リンカー オプション"
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /KEYCONTAINER (アセンブリに署名するためのキー コンテナーの指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/KEYCONTAINER:name  
```  
  
## 解説  
 指定項目  
  
 *name*  
 キーを含むコンテナー。  コンテナー名に空白が含まれている場合は、文字列を二重引用符 \(" "\) で囲みます。  
  
## 解説  
 リンカーは、公開キーをアセンブリ マニフェストに挿入し、秘密キーを使用して最後のアセンブリに署名することにより、署名されたアセンブリを作成します。  キー ファイルを生成するには、コマンド ラインで「[sn \-k](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) `file`」と入力します。  **sn \-i** を使用すると、キー ペアがコンテナーにインストールされます。  
  
 [\/LN](../../build/reference/ln-create-msil-module.md) を指定してコンパイルした場合は、キー ファイルの名前がモジュールに保持され、[\#using](../../preprocessor/hash-using-directive-cpp.md) を通じてモジュールへの明示的な参照を含むアセンブリをコンパイルしたとき、または [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) とリンクしたときに作成されるアセンブリに組み込まれます。  
  
 [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) を使用して、暗号に関する情報をコンパイラに渡すこともできます。  アセンブリに部分署名する場合は、[\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md) を使用します。  アセンブリに対する署名の詳細については、「[厳密名アセンブリ \(アセンブリ署名\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)」を参照してください。  
  
 このほかにも、次のようなリンカー オプションがアセンブリの生成に影響します。  
  
-   [\/ASSEMBLYDEBUG \(DebuggableAttribute の追加\)](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにオプションを入力します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)