---
title: "/MANIFEST (side-by-side アセンブリ マニフェストを作成する) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateManifest"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFEST リンカー オプション"
  - "MANIFEST リンカー オプション"
  - "-MANIFEST リンカー オプション"
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# /MANIFEST (side-by-side アセンブリ マニフェストを作成する)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFEST[:{EMBED[,ID=#]|NO}]  
```  
  
## 解説  
 \/MANIFEST は、リンカーが side\-by\-side マニフェストファイルを作成することを指定します。  マニフェスト ファイルの詳細については、「[Manifest Files Reference](http://msdn.microsoft.com/library/aa375632)」を参照してください。  
  
 既定値は、"\/MANIFEST" です。  
  
 \/MANIFEST:EMBED オプションは、リンカーが RT\_MANIFEST 型のリソースとしてイメージにマニフェスト ファイルを埋め込む必要があることを指定します。  省略可能な `ID` パラメーターは、マニフェストで使用するリソース ID です。  実行可能ファイルの場合は値 1 を使用します。  DLL の場合は値 2 を使用して、プライベート依存関係を指定できるようにします。  `ID` パラメーターを指定しない場合、\/DLL オプションが設定されている場合の既定値は 2、それ以外の場合の既定値は 1 になります。  
  
 [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] から、実行可能ファイルのマニフェスト ファイルには、ユーザー アカウント制御 \(UAC: User Account Control\) 情報を指定するセクションが含まれるようになりました。  \/MANIFEST を指定した状態で、[\/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md) と [\/DLL](../../build/reference/dll-build-a-dll.md) のいずれも指定していない場合、UAC レベルが *asInvoker* に設定されている既定の UAC フラグメントがマニフェストに挿入されます。  UAC レベルの詳細については、「[\/MANIFESTUAC \(UAC 情報をマニフェストに組み込む\)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)」を参照してください。  
  
 UAC の既定の動作を変更するには、次のいずれかを行います。  
  
-   \/MANIFESTUAC オプションを指定して、UAC レベルを所定の値に設定します。  
  
-   マニフェストに UAC フラグメントを生成しない場合は、\/MANIFESTUAC:NO オプションを指定します。  
  
 \/MANIFEST を指定せずに、[\/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md) コメントを指定する場合は、マニフェスト ファイルが作成されます。  \/MANIFEST:NO を指定すると、マニフェスト ファイルは作成されません。  
  
 \/MANIFEST を指定すると、マニフェスト ファイルの名前は出力ファイルの名前と同じになりますが、ファイル名に .manifest が追加されます。  たとえば、出力ファイルの名前が MyFile.exe の場合、マニフェスト ファイル名は MyFile.exe.manifest になります。\/MANIFESTFILE:*name* を指定すると、マニフェストの名前は、*name* で指定した名前になります。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[リンカー\]** ノードを展開します。  
  
4.  **\[マニフェスト ファイル\]** プロパティ ページをクリックします。  
  
5.  **\[マニフェストの生成\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)