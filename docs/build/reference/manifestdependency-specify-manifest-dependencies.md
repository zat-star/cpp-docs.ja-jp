---
title: "-MANIFESTDEPENDENCY (マニフェストの依存関係の指定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.AdditionalManifestDependencies
dev_langs: C++
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 01da83a57769dbe5b86c5bc2a73875231b769cdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (マニフェストの依存関係を指定する)
```  
/MANIFESTDEPENDENCY:manifest_dependency  
```  
  
## <a name="remarks"></a>コメント  
 /MANIFESTDEPENDENCY を使用してに配置される属性を指定できます、\<依存関係 > マニフェスト ファイルのセクションでします。  
  
 参照してください[/MANIFEST (作成サイド バイ サイド アセンブリ マニフェスト)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)マニフェスト ファイルを作成する方法についてはします。  
  
 詳細については、\<依存関係 > セクションで、マニフェスト ファイルの次を参照してください。[発行者構成ファイル](http://msdn.microsoft.com/library/aa375682)です。  
  
 /MANIFESTDEPENDENCY 情報は、2 つの方法のいずれかでリンカーに渡されることができます。  
  
-   (または応答ファイルで) コマンド ラインで直接/MANIFESTDEPENDENCY とします。  
  
-   使用して、[コメント](../../preprocessor/comment-c-cpp.md)プラグマ。  
  
 次の例では、プラグマ、経由で渡された/MANIFESTDEPENDENCY コメント  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 その結果、マニフェスト ファイルで次のエントリには。  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 同じ/MANIFESTDEPENDENCY コメントは、コマンドラインで渡されることができます。  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 リンカーは/MANIFESTDEPENDENCY コメントの収集、エントリの重複を排除し、マニフェスト ファイルに結果の XML 文字列を追加します。  場合は、リンカーは、競合しているエントリを検出し、マニフェスト ファイルが破損し、アプリケーションは起動に失敗 (エラーの原因を示す、イベント ログにはエントリを追加可能性があります)。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**マニフェスト ファイル**プロパティ ページ。  
  
5.  変更、**追加のマニフェストの依存関係**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)