---
title: "/KEYFILE (アセンブリに署名するためのキーまたはキー ペアの指定) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/keyfile"
  - "VC.Project.VCLinkerTool.KeyFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/KEYFILE リンカー オプション"
  - "KEYFILE リンカー オプション"
  - "-KEYFILE リンカー オプション"
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /KEYFILE (アセンブリに署名するためのキーまたはキー ペアの指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/KEYFILE:filename  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *filename*  
 キーを含むファイル。  コンテナー名に空白が含まれている場合は、文字列を二重引用符 \(" "\) で囲みます。  
  
## 解説  
 リンカーは、アセンブリ マニフェストに公開キーを挿入し、秘密キーを使用して最後のアセンブリに署名します。  キー ファイルを生成するには、コマンド ラインで「[sn \-k](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) `file`」と入力します。  署名されたアセンブリは、厳密な名前を持つアセンブリとなります。  
  
 [\/LN](../../build/reference/ln-create-msil-module.md) を指定してコンパイルした場合は、キー ファイルの名前がモジュールに保持され、[\#using](../../preprocessor/hash-using-directive-cpp.md) を通じてモジュールへの明示的な参照を含むアセンブリをコンパイルしたとき、または [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) とリンクしたときに作成されるアセンブリに組み込まれます。  
  
 [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) を使用して、暗号に関する情報をリンカーに渡すこともできます。  アセンブリに部分署名する場合は、[\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md) を使用します。  アセンブリに対する署名の詳細については、「[厳密名アセンブリ \(アセンブリ署名\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)」を参照してください。  
  
 コマンド ライン オプションまたはカスタム属性のいずれかを使用して **\/KEYFILE** と **\/KEYCONTAINER** の両方が指定されている場合、リンカーはまずキー コンテナーを探します。  コンテナーが検出された場合、アセンブリはキー コンテナーの情報で署名されます。  キー コンテナーが見つからない場合は、\/KEYFILE で指定されたファイルを探します。  成功すると、キー ファイル内の情報を使用して、アセンブリが署名されます。キー情報はキー コンテナーに組み込まれるため \(sn \-i と同じ\)、次回のコンパイルではキー コンテナーが有効になります。  
  
 キー ファイルには、公開キーだけが含まれていることがあります。  
  
 アセンブリの署名の詳細については、「[厳密な名前付きアセンブリの作成と使用](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)」を参照してください。  
  
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