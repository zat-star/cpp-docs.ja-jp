---
title: -DEFAULTLIB (既定のライブラリの指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
dev_langs:
- C++
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e48db05ea50917a09e618c782d86dace73a1bf7e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (既定のライブラリの指定)
```  
/DEFAULTLIB:library  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *ライブラリ*  
 外部参照を解決するときに検索するライブラリの名前。  
  
## <a name="remarks"></a>コメント  
 /DEFAULTLIB オプションは、1 を加算*ライブラリ*リンク参照の解決時に検索するライブラリの一覧にします。 /DEFAULTLIB で指定したライブラリは、.obj ファイル内の既定のライブラリの前に、コマンドラインで指定したライブラリ後が検索されます。  
  
 [すべて既定のライブラリの無視](../../build/reference/nodefaultlib-ignore-libraries.md)(/NODEFAULTLIB) オプションをオーバーライド/DEFAULTLIB:*ライブラリ*です。 [ライブラリの無視](../../build/reference/nodefaultlib-ignore-libraries.md)(/NODEFAULTLIB:*ライブラリ*) オプションをオーバーライド/DEFAULTLIB:*ライブラリ*とき同じ*ライブラリ*名は両方で指定します。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
-   このリンカー オプションでは、Visual Studio 開発環境から使用できません。 リンク時にライブラリを追加するには、使用、**追加の依存関係**プロパティから、**入力**プロパティ ページ。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)