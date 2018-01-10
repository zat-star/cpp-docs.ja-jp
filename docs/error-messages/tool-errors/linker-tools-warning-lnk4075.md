---
title: "リンカー ツールの警告 LNK4075 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4075
dev_langs: C++
helpviewer_keywords: LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8c3330e637ae0e0dce5e875fcc349c6deefcf27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4075"></a>リンカー ツールの警告 LNK4075
により「・ オプション 2」仕様「オプション 1」を無視しています  
  
 2 番目のオプションは、1 つをオーバーライドします。  
  
 相互に排他的なリンカー オプションが指定されます。  リンカー オプションを確認します。  リンカーのオプションが指定されているプロジェクトをビルドしている方法によって異なります。  
  
-   開発環境で作成する場合、[リンカー] プロパティ ページ、プロジェクトのファイルの場所し、リンカーの両方のオプションが指定されている場所を参照してください。  参照してください[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)詳細についてはします。  
  
-   コマンドラインでビルドする場合があります指定されたリンカー オプションを調べます。  
  
-   ビルド スクリプトでビルドする場合は、これらのリンカー オプションが指定されている、スクリプトで検索します。  
  
 相互に排他的なリンカー オプションが指定されているが見つかったら、リンカー オプションのいずれかを削除します。  
  
 具体的な例:  
  
-   コンパイルされたモジュールをリンクする場合は**/ZI**、内部リンカー オプションを意味すると、/EDITANDCONTINUE ものではありません、/EDITANDCONTINUE と/opt:ref による、/OPT:ICF、または、/INCREMENTAL:NO でコンパイルされたモジュールが呼び出されると、ダイアログが表示されますLNK4075 を取得します。  参照してください[/Z7、/Zi、/ZI (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md)詳細についてはします。