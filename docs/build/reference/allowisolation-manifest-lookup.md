---
title: "-/ALLOWISOLATION (マニフェスト検索) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
dev_langs: C++
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d0ca939021a6fc530b11c6ec66fc74cc012da1c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (マニフェスト検索)
マニフェスト検索の動作を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/ALLOWISOLATION[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 **/ALLOWISOLATION:NO**マニフェストがない場合、Dll が読み込まれることを示しますリンカーを設定して、 `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` optional ヘッダーのビット`DllCharacteristics`フィールドです。  
  
 **/ALLOWISOLATION**により、オペレーティング システムはマニフェストの検索と読み込みがします。  
  
 **/ALLOWISOLATION**既定値です。  
  
 実行可能ファイルの分離が無効、Windows ローダーは新しく作成されたプロセスのアプリケーション マニフェストを検索しません。 実行可能ファイルまたは名前を持つ実行可能ファイルと同じディレクトリに配置されている内部マニフェストがある場合でも、新しいプロセスは既定のアクティベーション コンテキストをありません*実行可能ファイル名***. exe.manifest**です。  
  
 詳細については、次を参照してください。 [Manifest Files Reference](http://msdn.microsoft.com/library/aa375632)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**マニフェスト ファイル**プロパティ ページ。  
  
5.  変更、**分離の許可**プロパティです。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)