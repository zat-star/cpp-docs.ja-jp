---
title: "-PGD (プロファイル ガイド付き最適化のデータベースの指定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.ProfileGuidedDatabase
dev_langs: C++
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 37113ef23adbbb50e36b51ed8ef0035ee20e885e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (ガイド付き最適化のプロファイル用のデータベースの指定)
/PGD:`filename`  
  
## <a name="remarks"></a>コメント  
 ここで、  
  
 `filename`  
 実行中のプログラムに関する情報を保持するために使用される .pgd ファイルの名前を指定します。  
  
## <a name="remarks"></a>コメント  
 使用する場合[/LTCG:PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md)/PGD を使用して、既定以外の名前または .pgd ファイルの場所を指定します。 /PGD を指定しないと、.pgd ファイル名は、出力ファイル (.exe または .dll) 名と同じになり、リンクの呼び出し元となる同じディレクトリに作成されます。  
  
 /LTCG:PGOPTIMIZE を使用する場合は、/PGD を使用して、使用して、最適化されたイメージを作成する .pgd ファイルの名前を指定します。  
  
 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**最適化**プロパティ ページ。  
  
5.  変更、**プロファイル ガイド付きデータベース**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)