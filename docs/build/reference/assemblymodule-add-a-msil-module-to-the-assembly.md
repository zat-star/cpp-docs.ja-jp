---
title: "/ASSEMBLYMODULE (MSIL モジュールのアセンブリへの追加) | Microsoft Docs"
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
  - "/assemblymodule"
  - "VC.Project.VCLinkerTool.AddModuleNamesToAssembly"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYMODULE リンカー オプション"
  - "アセンブリ [C++]"
  - "アセンブリ [C++], 追加 (モジュールを)"
  - "ASSEMBLYMODULE リンカー オプション"
  - "-ASSEMBLYMODULE リンカー オプション"
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYMODULE (MSIL モジュールのアセンブリへの追加)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYMODULE:filename  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *filename*  
 このアセンブリに含めるモジュール。  
  
## 解説  
 \/ASSEMBLYMODULE オプションを使用して、アセンブリにモジュール参照を追加できます。  モジュール参照を追加したアセンブリ プログラムでは、モジュールのタイプ情報を使用できません。  ただし、アセンブリを参照するすべてのプログラムで、モジュールのタイプ情報を使用できます。  
  
 [\#using](../../preprocessor/hash-using-directive-cpp.md) を使用すると、アセンブリにモジュール参照を追加し、モジュールのタイプ情報をアセンブリ プログラムで使用できます。  
  
 たとえば、次のような方法もあります。  
  
1.  [\/LN](../../build/reference/ln-create-msil-module.md) を指定してモジュールを作成します。  
  
2.  別のプロジェクトで、\/ASSEMBLYMODULE を使用して現在のコンパイルにモジュールを含め、アセンブリを作成します。  このプロジェクトでは、`#using` によるモジュールの参照は行いません。  
  
3.  これで、このアセンブリを参照するすべてのプロジェクトで、モジュールのタイプを使用できます。  
  
 このほかにも、次のようなリンカー オプションがアセンブリの生成に影響します。  
  
-   [\/ASSEMBLYDEBUG \(DebuggableAttribute の追加\)](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Visual C\+\+ リンカーは、入力、リンカーによって生成される出力ファイルはリンカーに渡された .netmodules のいずれかへの実行時に依存しないアセンブリまたは"であるため .netmodule ファイルをリンクできます。詳細については、「[リンカー入力としての .netmodule ファイル](../Topic/.netmodule%20Files%20as%20Linker%20Input.md)」を参照してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[入力\] プロパティ ページをクリックします。  
  
4.  \[モジュールをアセンブリに追加\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)