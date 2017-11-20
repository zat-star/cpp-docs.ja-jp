---
title: "分析 (コード分析) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
dev_langs: C++
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b640d042f1f8a30246f4d7277a8a5b001722acd9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="analyze-code-analysis"></a>/analyze (コード分析)
コード分析とコントロール オプションを有効にします。  
  
## <a name="syntax"></a>構文  
  
```  
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only]  
```  
  
## <a name="arguments"></a>引数  
 /analyze  
 既定のモードで分析をオンにします。 分析の出力に送ら、**出力**他のエラー メッセージのようなウィンドウ。 使用して**/analyze -**分析を明示的にオフにします。  
  
 /analyze:WX-  
 指定する**/analyze: WX -**を使用してコンパイルするときにコード分析警告することを意味がエラーとして扱われません**/WX**です。 詳細については、「[/w、/W0、/W1、/W2、/W3、/W4, /w1, /w2, /w3、/w4、/Wall、/wd、/we、/wo、/Wv、/WX (警告レベル)](../../build/reference/compiler-option-warning-level.md)」を参照してください。  
  
 /analyze:log `filename`  
 詳細なアナライザーの結果が、`filename` で指定されたファイルに XML として書き込まれます。  
  
 /analyze:quiet  
 アナライザーの出力をオフに、**出力**ウィンドウです。  
  
 /analyze:stacksize `number`  
 `number`パラメーターは、このオプションと共に使用される、サイズのバイトで指定、警告のスタック フレーム[C6262](/visualstudio/code-quality/c6262)が生成されます。 このパラメーターが指定されていない場合は、既定の 16 KB がスタック フレーム サイズとして使用されます。  
  
 /analyze:max_paths `number`  
 このオプションと共に使用される `number` パラメーターでは、分析するコード パスの最大数を指定します。 このパラメーターが指定されていない場合は、既定の 256 が最大数として使用されます。 値を大きくすると、より細かなチェックが実行されますが、分析に時間がかかることがあります。  
  
 /analyze:only  
 通常、コンパイラは、アナライザーを実行した後にコードを生成し、構文チェックをさらに実行します。 **/Analyze: のみ**オプションは、このコード生成パスによってオフ以外の場合はこのため、分析を高速化がコンパイル エラーと、コンパイラのコード生成パスによって検出された警告が出力されません。 プログラムにコード生成のエラーがある場合は、分析結果が信頼できないものになる可能性があるため、このオプションを使用するのは、コードが既にコード生成構文チェックをエラーなしで渡している場合だけにすることをお勧めします。  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [C と C++ の概要のコード分析](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)と[c/c++ の警告のコード分析](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**コード分析**ノード。  
  
4.  **[全般]** プロパティ ページをクリックします。  
  
5.  1 つ以上の変更、**コード分析**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)