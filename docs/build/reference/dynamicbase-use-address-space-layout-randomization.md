---
title: -DYNAMICBASE (使用するアドレス領域のレイアウトのランダム化) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.RandomizedBaseAddress
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE linker option
- /DYNAMICBASE linker option
- DYNAMICBASE linker option
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85af66c4ce05057eff63292061b66202aeebe160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="dynamicbase-use-address-space-layout-randomization"></a>/DYNAMICBASE (ASLR (Address Space Layout Randomization) の使用)
ランダムにリベースできる負荷時の address space layout randomization (機能) 機能を使用して、実行可能イメージを生成するかどうかを示す[!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]です。  
  
## <a name="syntax"></a>構文  
  
```  
/DYNAMICBASE[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 既定では、/DYNAMICBASE しています  
  
 このオプションは、ロード時にアプリケーションをランダムにリベースするかどうかを示すように実行可能ファイルのヘッダーを変更します。  
  
 アドレス空間のレイアウトのランダム化はサポートされて[!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]です。  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**詳細**プロパティ ページ。  
  
5.  変更、**のベース アドレスのランダム化された**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)