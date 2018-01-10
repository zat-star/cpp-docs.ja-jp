---
title: "-INCLUDE (シンボル参照の強制) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
dev_langs: C++
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8caf060d278e7ac2c92c38ad58e9c4c55eab632c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="include-force-symbol-references"></a>/INCLUDE (シンボルの明示的な参照)
```  
/INCLUDE:symbol  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 `symbol`  
 シンボル テーブルに追加する記号を指定します。  
  
## <a name="remarks"></a>コメント  
 /INCLUDE オプションを使用すると、リンカーは、指定されたシンボルをシンボル テーブルに追加します。  
  
 複数のシンボルを指定するには、コンマ (,)、セミコロン (;)、またはシンボル名の間にスペースを入力します。 コマンド ラインで指定/INCLUDE:`symbol`シンボルごとに 1 回です。  
  
 リンカーが解決`symbol`プログラムするシンボル定義を含むオブジェクトを追加しています。 この機能は、それ以外の場合、プログラムにはリンクいないライブラリ オブジェクトを含める場合に便利です。  
  
 このオプションを使用してシンボルを指定することによってそのシンボルの削除をオーバーライドします[/opt:ref による](../../build/reference/opt-optimizations.md)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**入力**プロパティ ページ。  
  
4.  変更、**シンボル参照の強制**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)