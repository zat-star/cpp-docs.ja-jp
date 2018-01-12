---
title: "-TLBOUT (名前です。TLB ファイル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.TypeLibraryFile
- /tlbout
dev_langs: C++
helpviewer_keywords:
- tlb files, renaming
- TLBOUT linker option
- /TLBOUT linker option
- .tlb files, renaming
- -TLBOUT linker option
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c898121a4ac29cc05022504ebfe33949b44eca7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT (.TLB ファイル名の指定)
```  
/TLBOUT:[path\]filename  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *path*  
 .Tlb ファイルを作成する必要がの絶対または相対パスを指定します。  
  
 *ファイル名*  
 MIDL コンパイラによって作成された .tlb ファイルの名前を指定します。 ファイル拡張子は付加されません。指定*filename*.tlb 拡張子 .tlb を付加する場合。  
  
## <a name="remarks"></a>コメント  
 /TLBOUT オプションは、名前と、.tlb ファイルの拡張子を指定します。  
  
 MIDL コンパイラを持つプロジェクトをリンクするときに、Visual C リンカーによって呼び出されます。、[モジュール](../../windows/module-cpp.md)属性。  
  
 .Tlb ファイルがからその名前を取得/TLBOUT が指定されていない場合[/IDLOUT](../../build/reference/idlout-name-midl-output-files.md) *filename*です。 /IDLOUT が指定されていない場合、.tlb ファイルには、vc70.tlb が呼び出されます。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**埋め込み IDL**プロパティ ページ。  
  
4.  変更、**タイプ ライブラリ**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [/IGNOREIDL (しない属性の処理を MIDL に挿入)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/MIDL (MIDL コマンド ライン オプションの指定)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [属性付きプログラムの作成](../../windows/building-an-attributed-program.md)