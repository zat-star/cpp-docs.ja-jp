---
title: "-GH (_pexit フック関数の有効化) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _pexit
dev_langs:
- C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02cfdd783a698a3397e84fa62b7252399570dc84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="gh-enable-pexit-hook-function"></a>/GH (_pexit フック関数の有効化)
呼び出し、`_pexit`関数すべてのメソッドまたは関数の末尾。  
  
## <a name="syntax"></a>構文  
  
```  
/GH  
```  
  
## <a name="remarks"></a>コメント  
 `_pexit`関数は、任意のライブラリの一部ではないの定義を指定するかどうかは`_pexit`します。  
  
 明示的に呼び出す予定がない限り`_pexit`プロトタイプを提供する必要はありません。 関数は、する必要がありますとして記述があった次のプロトタイプでは、エントリのすべてのレジスタのコンテンツをプッシュおよび終了時に変更されていないコンテンツを表示する必要があります。  
  
```  
void __declspec(naked) _cdecl _pexit( void );  
```  
  
 `_pexit`ような`_penter`; を参照してください[/Gh (有効にする _penter フック関数)](../../build/reference/gh-enable-penter-hook-function.md)を記述する方法の例については、`_pexit`関数。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)