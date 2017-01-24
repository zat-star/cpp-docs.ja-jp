---
title: "ビルドのコマンドとプロパティのマクロ | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles"
  - "VC.Project.VCCLCompilerTool.XMLDocumentationFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "$(ConfigurationName) マクロ"
  - "$(DevEnvDir) マクロ"
  - "$(FrameworkDir) マクロ"
  - "$(FrameworkSDKDir) マクロ"
  - "$(FrameworkVersion) マクロ"
  - "$(FxCopDir) マクロ"
  - "$(Inherit) マクロ"
  - "$(InputDir) マクロ"
  - "$(InputExt) マクロ"
  - "$(InputFileName) マクロ"
  - "$(InputName) マクロ"
  - "$(InputPath) マクロ"
  - "$(IntDir) マクロ"
  - "$(NoInherit) マクロ"
  - "$(OutDir) マクロ"
  - "$(ParentName) マクロ"
  - "$(PlatformName) マクロ"
  - "$(ProjectDir) マクロ"
  - "$(ProjectExt) マクロ"
  - "$(ProjectFileName) マクロ"
  - "$(ProjectName) マクロ"
  - "$(ProjectPath) マクロ"
  - "$(References) マクロ"
  - "$(RemoteMachine) マクロ"
  - "$(RootNamespace) マクロ"
  - "$(SafeRootNamespace) マクロ"
  - "$(SolutionDir) マクロ"
  - "$(SolutionExt) マクロ"
  - "$(SolutionFileName) マクロ"
  - "$(SolutionName) マクロ"
  - "$(SolutionPath) マクロ"
  - "$(StopEvaluating) マクロ"
  - "$(TargetDir) マクロ"
  - "$(TargetExt) マクロ"
  - "$(TargetFileName) マクロ"
  - "$(TargetName) マクロ"
  - "$(TargetPath) マクロ"
  - "$(VCInstallDir) マクロ"
  - "$(VSInstallDir) マクロ"
  - "$(WebDeployPath) マクロ"
  - "$(WebDeployRoot) マクロ"
  - "ビルド マクロ [C++]"
  - "ビルド [C++], マクロ"
  - "ConfigurationName マクロ $(ConfigurationName)"
  - "DevEnvDir マクロ $(DevEnvDir)"
  - "FrameworkDir マクロ $(FrameworkDir)"
  - "FrameworkSDKDir マクロ $(FrameworkSDKDir)"
  - "FrameworkVersion マクロ $(FrameworkVersion)"
  - "FxCopDir マクロ $(FxCopDir)"
  - "Inherit マクロ $(Inherit)"
  - "InputDir マクロ $(InputDir)"
  - "InputExt マクロ $(InputExt)"
  - "InputFileName マクロ $(InputFileName)"
  - "InputName マクロ $(InputName)"
  - "InputPath マクロ $(InputPath)"
  - "IntDir マクロ $(IntDir)"
  - "マクロ [C++], ビルド マクロ"
  - "NoInherit マクロ $(NoInherit)"
  - "OutDir マクロ $(OutDir)"
  - "ParentName マクロ $(ParentName)"
  - "PlatformName マクロ $(PlatformName)"
  - "ProjectDir マクロ $(ProjectDir)"
  - "ProjectExt マクロ $(ProjectExt)"
  - "ProjectFileName マクロ $(ProjectFileName)"
  - "ProjectName マクロ $(ProjectName)"
  - "ProjectPath マクロ $(ProjectPath)"
  - "プロパティ [C++], ビルド プロパティ マクロ"
  - "References マクロ $(References)"
  - "RemoteMachine マクロ $(RemoteMachine)"
  - "RootNamespace マクロ $(RootNamespace)"
  - "SafeRootNamespace マクロ $(SafeRootNamespace)"
  - "SolutionDir マクロ $(SolutionDir)"
  - "SolutionExt マクロ $(SolutionExt)"
  - "SolutionFileName マクロ $(SolutionFileName)"
  - "SolutionName マクロ $(SolutionName)"
  - "SolutionPath マクロ $(SolutionPath)"
  - "StopEvaluating マクロ $(StopEvaluating)"
  - "TargetDir マクロ $(TargetDir)"
  - "TargetExt マクロ $(TargetExt)"
  - "TargetFileName マクロ $(TargetFileName)"
  - "TargetName マクロ $(TargetName)"
  - "TargetPath マクロ $(TargetPath)"
  - "VCInstallDir マクロ $(VCInstallDir)"
  - "VSInstallDir マクロ $(VSInstallDir)"
  - "WebDeployPath マクロ $(WebDeployPath)"
  - "WebDeployRoot マクロ $(WebDeployRoot)"
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
caps.latest.revision: 22
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ビルドのコマンドとプロパティのマクロ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のマクロは、プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックス内の、文字列を入力できるどの場所にも使用できます。 これらのマクロの大文字と小文字は区別されません。  
  
 現在使用可能なマクロを表示するには、プロパティ名の右側の列で、ドロップダウン矢印をクリックします。**\[編集\]** が使用可能な場合は、\[編集\] をクリックし、編集ダイアログ ボックスで **\[マクロ\]** をクリックします。 詳細については、「[プロパティ ページ](../ide/property-pages-visual-cpp.md)」の「**Specifying User\-Defined Values**」セクションを参照してください。  
  
 「非推奨」とマークされたマクロは使用できないか、同等の[項目メタデータ マクロ](../Topic/ItemMetadata%20Element%20\(MSBuild\).md) \(**%\(***name***\)**\) と置き換えられています。 "非推奨。移行済みです" とマークされたマクロも使用できません。 さらに、そのマクロを含むプロジェクトが Visual Studio 2008 から移行された場合、Visual Studio はそのマクロを同等の現在のマクロに変換します。  
  
|マクロ|説明|  
|---------|--------|  
|**$\(RemoteMachine\)**|\[デバッグ\] プロパティ ページで **Remote Machine**  プロパティの値を設定します。 詳細については、「[C または C\+\+ デバッグ構成のプロジェクト設定](../Topic/Project%20Settings%20for%20a%20C++%20Debug%20Configuration.md)」を参照してください。|  
|**$\(Configuration\)**|現在のプロジェクト構成の名前 \(例: "Debug"\) です。|  
|**$\(Platform\)**|現在のプロジェクト プラットフォームの名前 \(例: "Win32"\) です。|  
|**$\(ParentName\)**|\(非推奨\) このプロジェクト項目を含む項目の名前です。 これは、親フォルダー名またはプロジェクト名になります。|  
|**$\(RootNameSpace\)**|アプリケーションを含む名前空間 \(定義されている場合\) です。|  
|**$\(IntDir\)**|中間ファイルに指定されたディレクトリへのパスです。 これが相対パスの場合、中間ファイルはこのパスを通じてプロジェクト ディレクトリに追加されます。 このパスの末尾にはスラッシュが必要です。 これは **Intermediate Directory** プロパティの値に解決されます。**$\(OutDir\)** を使用して、このプロパティを定義しないでください。|  
|**$\(OutDir\)**|出力ファイルのディレクトリへのパスです。 これが相対パスの場合、出力ファイルはこのパスを通じてプロジェクト ディレクトリに追加されます。 このパスの末尾にはスラッシュが必要です。 これは **Output Directory** プロパティの値に解決されます。**$\(IntDir\)** を使用して、このプロパティを定義しないでください。|  
|**$\(DevEnvDir\)**|Visual Studio のインストール ディレクトリ \(ドライブ \+ パスで定義\) です。最後に円記号 \(\\\) が含まれます。|  
|**$\(InputDir\)**|\(非推奨。移行済みです。\) 入力ファイルのディレクトリ \(ドライブ \+ パスで定義\) です。最後に円記号 \(\\\) が含まれます。 プロジェクトが入力の場合、このマクロは **$\(ProjectDir\)** と同等です。|  
|**$\(InputPath\)**|\(非推奨。移行済みです。\) 入力ファイルの絶対パス名 \(ドライブ \+ パス \+ 基本名 \+ ファイル拡張子で定義\) です。 プロジェクトが入力の場合、このマクロは **$\(ProjectPath\)** と同等です。|  
|**$\(InputName\)**|\(非推奨。移行済みです。\) 入力ファイルの基本名です。 プロジェクトが入力の場合、このマクロは **$\(ProjectName\)** と同等です。|  
|**$\(InputFileName\)**|\(非推奨。移行済みです。\) 入力ファイルの名前 \(基本名 \+ ファイル拡張子で定義\) です。 プロジェクトが入力の場合、このマクロは **$\(ProjectFileName\)** と同等です。|  
|**$\(InputExt\)**|\(非推奨。移行済みです。\) 入力ファイルのファイル拡張子。 ファイル拡張子の前にピリオド '.' が付きます。 プロジェクトが入力の場合、このマクロは **$\(ProjectExt\)** と同等です。|  
|**$\(ProjectDir\)**|プロジェクトのディレクトリ \(ドライブ \+ パスで定義\) です。最後に円記号 \(\\\) が含まれます。|  
|**$\(ProjectPath\)**|プロジェクトの絶対パス名 \(ドライブ \+ パス \+ 基本名 \+ ファイル拡張子で定義\) です。|  
|**$\(ProjectName\)**|プロジェクトの基本名です。|  
|**$\(ProjectFileName\)**|プロジェクトのファイル名 \(基本名 \+ ファイル拡張子で定義\) です。|  
|**$\(ProjectExt\)**|プロジェクトのファイル拡張子。 ファイル拡張子の前にピリオド '.' が付きます。|  
|**$\(SolutionDir\)**|ソリューションのディレクトリ \(ドライブ \+ パスで定義\) です。最後に円記号 \(\\\) が含まれます。|  
|**$\(SolutionPath\)**|ソリューションの絶対パス名 \(ドライブ \+ パス \+ 基本名 \+ ファイル拡張子で定義\) です。|  
|**$\(SolutionName\)**|ソリューションの基本名です。|  
|**$\(SolutionFileName\)**|ソリューションのファイル名 \(基本名 \+ ファイル拡張子で定義\) です。|  
|**$\(SolutionExt\)**|ソリューションのファイル拡張子です。 ファイル拡張子の前にピリオド '.' が付きます。|  
|**$\(TargetDir\)**|ビルドのプライマリ出力ファイルのディレクトリ \(ドライブ \+ パスで定義\) です。最後に円記号 \(\\\) が含まれます。|  
|**$\(TargetPath\)**|ビルドのプライマリ出力ファイルの絶対パス名 \(ドライブ \+ パス \+ 基本名 \+ ファイル拡張子で定義\) です。|  
|**$\(TargetName\)**|ビルドのプライマリ出力ファイルの基本名です。|  
|**$\(TargetFileName\)**|ビルドのプライマリ出力ファイルの名前 \(基本名 \+ ファイル拡張子で定義\) です。|  
|**$\(TargetExt\)**|ビルドのプライマリ出力ファイルのファイル拡張子。 ファイル拡張子の前にピリオド '.' が付きます。|  
|**$\(VSInstallDir\)**|Visual Studio をインストールしたディレクトリです。<br /><br /> このプロパティにはターゲットの Visual Studio のバージョンが含まれますが、ホストの Visual Studio とは異なることがあります。 たとえば、`$(PlatformToolset) = v110` を設定してビルドした場合、**$\(VSInstallDir\)** には Visual Studio 2012 インストールへのパスが含まれます。|  
|**$\(VCInstallDir\)**|Visual C\+\+ をインストールしたディレクトリです。<br /><br /> このプロパティにはターゲットの Visual C\+\+ のバージョンが含まれますが、ホストの Visual C\+\+ とは異なることがあります。 たとえば、`$(PlatformToolset) = v90` を設定してビルドした場合、**$\(VCInstallDir\)** にはVisual C\+\+ 2008 インストールへのパスが含まれます。|  
|**$\(FrameworkDir\)**|.NET Framework をインストールしたディレクトリです。|  
|**$\(FrameworkVersion\)**|Visual Studio が使用する .NET Framework のバージョンです。**$\(FrameworkDir\)** と組み合わせると、Visual Studio が使用する .NET Framework のバージョンへの完全なパスになります。|  
|**$\(FrameworkSDKDir\)**|.NET Framework をインストールしたディレクトリです。 .NET Framework は、Visual Studio 一部としてインストールされている場合も、個別にインストールされている場合もあります。|  
|**$\(WebDeployPath\)**|Web 配置のルートから、プロジェクト出力が存在するディレクトリへの相対パスです。<xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A> と同じ値を返します。|  
|**$\(WebDeployRoot\)**|**\<localhost\>** への絶対パスです。 たとえば、c:\\inetpub\\wwwroot などです。|  
|**$\(SafeParentName\)**|\(非推奨\) 有効な名前形式で指定された、直接の親の名前です。 たとえば、フォームは .resx ファイルの親です。|  
|**$\(SafeInputName\)**|\(非推奨\) 有効なクラス名としてのファイル名です。ファイル拡張子は除きます。|  
|**$\(SafeRootNamespace\)**|\(非推奨\) プロジェクト ウィザードでコードが追加される名前空間の名前です。 この名前空間名には、有効な C\+\+ 識別子で許可される文字列だけが含まれます。|  
|**$\(FxCopDir\)**|fxcop.cmd ファイルへのパスです。 fxcop.cmd ファイルは、Visual C\+\+ のすべてのエディションでインストールされるとは限りません。|  
  
## 参照  
 [Visual Studio での C\+\+ プロジェクトのビルド](../ide/building-cpp-projects-in-visual-studio.md)