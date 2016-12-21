---
title: "/ASSEMBLYLINKRESOURCE (.NET Framework リソースへのリンク) | Microsoft Docs"
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
  - "/ASSEMBLYLINKRESOURCE"
  - "VC.Project.VCLinkerTool.AssemblyLinkResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYLINKRESOURCE リンカー オプション"
  - "ASSEMBLYLINKRESOURCE リンカー オプション"
  - "-ASSEMBLYLINKRESOURCE リンカー オプション"
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYLINKRESOURCE (.NET Framework リソースへのリンク)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYLINKRESOURCE:filename  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *filename*  
 アセンブリからのリンク先である .NET Framework リソース ファイル。  
  
## 解説  
 \/ASSEMBLYLINKRESOURCE オプションは、出力ファイル内での .NET Framework リソースへのリンクを作成します。このリソース ファイルは出力ファイル内には含まれません。  リソース ファイルを出力ファイルに埋め込むには、[\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) を使用します。  
  
 リンカーで作成したアセンブリのリンク リソースはパブリックです。  
  
 \/ASSEMBLYLINKRESOURCE では、コンパイルに [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) を含める必要があります。[\/LN](../../build/reference/ln-create-msil-module.md) または [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) は、\/ASSEMBLYLINKRESOURCE では使用できません。  
  
 たとえば、*filename* が [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) によって作成された .NET Framework リソース ファイルである場合、または開発環境で作成された .NET Framework リソース ファイルである場合は、**System.Resources** 名前空間のメンバーを使用してアクセスできます。  詳細については、「[System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx)」を参照してください。  その他のすべてのリソースの場合は、**System.Reflection.Assembly** クラスの **GetManifestResource**\* メソッドを使用して実行時にリソースにアクセスします。  
  
 *filename* には任意のファイル形式を指定できます。  たとえば、ネイティブ DLL をアセンブリの一部として含め、そのネイティブ DLL をグローバル アセンブリ キャッシュにインストールして、アセンブリ内のマネージ コードからアクセスできるようにすることもできます。  
  
 このほかにも、次のようなリンカー オプションがアセンブリの生成に影響します。  
  
-   [\/ASSEMBLYDEBUG \(DebuggableAttribute の追加\)](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
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