---
title: "-FUNCTIONPADMIN (ホットパッチ可能なイメージの作成) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /functionpadmin
dev_langs:
- C++
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f737cdb412420ffb87664024b2314941e67b045b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (ホットパッチ可能なイメージの作成)
ホットパッチ用のイメージを準備します。  
  
## <a name="syntax"></a>構文  
  
```  
/FUNCTIONPADMIN[:space]  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `space` (省略可能)  
 各関数の先頭に追加するパディングの量 5、6、または 16。  x86 イメージが必要に 5 つのバイトのパディング、x64 イメージが必要に 6 バイト、および Itanium プロセッサ ファミリ用にビルドされたイメージは 16 バイトの各関数の先頭に埋め込みを必要とします。  
  
 既定では、コンパイラは、イメージとイメージのコンピューターの種類に基づいて、正しい領域の量を追加します。  
  
 ホットパッチ可能なイメージを生成するために、リンカーの順番は、.obj ファイル必要がありますしてコンパイルされている[/hotpatch (ホットパッチ可能なイメージの作成)](../../build/reference/hotpatch-create-hotpatchable-image.md)です。  
  
 コンパイルして単一の cl.exe、呼び出しでイメージを関連付ける**/hotpatch**意味**/functionpadmin**です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  オプションを入力、**追加オプション**ボックス。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)