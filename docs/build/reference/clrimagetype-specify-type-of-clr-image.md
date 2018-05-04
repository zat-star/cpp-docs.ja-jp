---
title: -CLRIMAGETYPE (CLR イメージの種類の指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
dev_langs:
- C++
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 003286d9c1445dec40a6dc0f595eda42f39947aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (CLR イメージのタイプの指定)
```  
/CLRIMAGETYPE:{IJW|PURE|SAFE|SAFE32BITPREFERRED}  
```  
  
## <a name="remarks"></a>コメント  
 リンカーは、ネイティブ オブジェクトを受け取り、MSIL オブジェクトを使用してコンパイルされるも[/clr](../../build/reference/clr-common-language-runtime-compilation.md)です。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは、Visual Studio 2015 で使用されなくなった。 同じビルドに混在するオブジェクトを渡すと、生成される出力ファイルの検証可能性は、既定で入力モジュールの最低レベルの検証可能性と等しくなります。 たとえば、ネイティブ イメージと混合モード イメージを渡す場合 (を使用してコンパイル **/clr**)、結果のイメージは混合モード イメージになります。  
  
 /CLRIMAGETYPE を使用すると、必要に応じてより低い検証可能性を指定できます。  
  
 ファイルの CLR イメージのタイプを判断する方法については、「 [/CLRHEADER](../../build/reference/clrheader.md)」を参照してください。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**詳細**プロパティ ページ。  
  
5.  変更、 **CLR イメージ タイプ**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)