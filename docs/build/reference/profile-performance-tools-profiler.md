---
title: "プロファイル (パフォーマンス ツール プロファイラー) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.Profile
dev_langs: C++
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54aff4c81b0bff9fcd6727333ee7d17c76564c71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (パフォーマンス ツール プロファイラー)
パフォーマンス ツール プロファイラーで使用できる出力ファイルを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
/PROFILE  
```  
  
## <a name="remarks"></a>コメント  
 /プロファイルは、次のリンカー オプションを意味します。  
  
-   [/OPT: REF](../../build/reference/opt-optimizations.md)  
  
-   /OPT: NOICF  
  
-   [/INCREMENTAL: いいえ](../../build/reference/incremental-link-incrementally.md)  
  
-   [/FIXED: いいえ](../../build/reference/fixed-fixed-base-address.md)  
  
 /PROFILE リンカーに、プログラム イメージの再配置セクションを生成します。  再配置セクションでは、プロファイル データを取得する、プログラム イメージを変換するプロファイラーを許可します。  
  
 **/プロファイル**はのみ Enterprise (チーム開発) バージョンでのみ使用できます。  PREfast の詳細については、次を参照してください。 [C と C++ の概要のコード分析](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**詳細**プロパティ ページ。  
  
5.  変更、**プロファイル**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)