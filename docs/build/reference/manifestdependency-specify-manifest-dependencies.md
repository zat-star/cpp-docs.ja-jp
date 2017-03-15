---
title: "/MANIFESTDEPENDENCY (マニフェストの依存関係を指定する) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.AdditionalManifestDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTDEPENDENCY リンカー オプション"
  - "MANIFESTDEPENDENCY リンカー オプション"
  - "-MANIFESTDEPENDENCY リンカー オプション"
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /MANIFESTDEPENDENCY (マニフェストの依存関係を指定する)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFESTDEPENDENCY:manifest_dependency  
```  
  
## 解説  
 \/MANIFESTDEPENDENCY を使用すると、マニフェスト ファイルの依存セクションに含まれる属性を指定できます。\>  \<  
  
 マニフェスト ファイルを作成する方法については、「[\/MANIFEST \(side\-by\-side アセンブリ マニフェストを作成する\)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)」を参照してください。  
  
 マニフェスト ファイルの \<\> dependency セクションの詳細については、「[Publisher Configuration Files](http://msdn.microsoft.com/library/aa375682)」を参照してください。  
  
 \/MANIFESTDEPENDENCY 情報は、次の 2 つの方法のどちらかでリンカーに渡すことができます。  
  
-   コマンド ラインで直接 \(または応答ファイルで\) \/MANIFESTDEPENDENCY を指定します。  
  
-   [comment](../../preprocessor/comment-c-cpp.md) プラグマを経由して渡します。  
  
 プラグマ経由で渡される \/MANIFESTDEPENDENCY コメントを次の例に示します。  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 この結果、マニフェスト ファイルに次のエントリが含まれます。  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 同じ \/MANIFESTDEPENDENCY コメントを次のようにコマンド ラインで渡すこともできます。  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 リンカーは、\/MANIFESTDEPENDENCY コメントを収集し、重複エントリを削除した結果として得られる XML 文字列をマニフェスト ファイルに追加します。リンカーが競合するエントリを検出した場合、マニフェスト ファイルは破損し、アプリケーションの起動は失敗します \(失敗の原因を示すためにエントリがイベント ログに追加される場合があります\)。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[リンカー\]** ノードを展開します。  
  
4.  **\[マニフェスト ファイル\]** プロパティ ページをクリックします。  
  
5.  **\[追加のマニフェスト依存関係\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)