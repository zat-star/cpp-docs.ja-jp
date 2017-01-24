---
title: "/ASSEMBLYRESOURCE (マネージ リソースの埋め込み) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.EmbedManagedResourceFile"
  - "/ASSEMBLYRESOURCE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYRESOURCE リンカー オプション"
  - "アセンブリ [C++]"
  - "アセンブリ [C++], リンク (リソース ファイルを)"
  - "ASSEMBLYRESOURCE リンカー オプション"
  - "-ASSEMBLYRESOURCE リンカー オプション"
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYRESOURCE (マネージ リソースの埋め込み)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]  
```  
  
## パラメーター  
 *filename*  
 このアセンブリに埋め込むマネージ リソース。  
  
 *name*  
 省略可能。  リソースの論理名。リソースを読み込むときに使用します。  既定値はファイル名です。  
  
 オプションとして、ファイルをアセンブリ マニフェスト内でプライベートにするかどうかを指定できます。  既定では、*name* はアセンブリ内でパブリックです。  
  
## 解説  
 \/ASSEMBLYRESOURCE オプションを使用して、アセンブリにリソースを埋め込みます。  
  
 リンカーで作成したアセンブリのリソースはパブリックです。  アセンブリのリソース名の変更は許可されません。  
  
 *filename* に指定したファイルが、たとえば、[リソース ファイル ジェネレーター \(Resgen.exe\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) で作成されたか、開発環境で作成された .NET Framework リソース \(.resources\) ファイルの場合は、**System.Resources** 名前空間のメンバーを使用してリソースにアクセスできます。詳細については、「[ResourceManager クラス](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx)」を参照してください。  他のすべてのリソースでは、**System.Reflection.Assembly** クラスの **GetManifestResource**\* メソッドを使用して実行時にリソースにアクセスします。  
  
 このほかにも、次のようなリンカー オプションがアセンブリの生成に影響します。  
  
-   [\/ASSEMBLYDEBUG \(DebuggableAttribute の追加\)](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[入力\] プロパティ ページをクリックします。  
  
4.  \[埋め込みマネージ リソース ファイル\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)