---
title: "-GT (サポート ファイバー セーフ スレッド ローカル ストレージ) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
dev_langs: C++
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5912f241716bbaf9aba989dabbeb25d38ab465c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>/GT (スレッド ローカル ストレージを使用したファイバー保護のサポート)
静的スレッド ローカル ストレージに割り当てられたデータを使用して割り当てられたデータに対して、ファイバー保護をサポートしている`__declspec(thread)`です。  
  
## <a name="syntax"></a>構文  
  
```  
/GT  
```  
  
## <a name="remarks"></a>コメント  
 宣言されたデータ`__declspec(thread)`スレッド ローカル ストレージ (TLS) の配列を参照します。 TLS 配列は、各スレッドに対して、システムが保持しているアドレスの配列です。 この配列の各アドレスは、スレッド ローカル ストレージのデータの場所を指定します。  
  
 ファイバーは、軽量オブジェクトをスタックとレジスタのコンテキストで構成され、さまざまなスレッドでスケジュールできます。 ファイバーは、任意のスレッドで実行できます。 ファイバーはスワップ アウトが後に別のスレッドで再起動ため、TLS 配列のアドレス必要がありますいないキャッシュまたは最適化される、共通部分式として関数呼び出しにわたる (を参照してください、 [/Og (グローバルの最適化)](../../build/reference/og-global-optimizations.md)のオプション詳細)。 **/GT**このような最適化を防止します。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**最適化**プロパティ ページ。  
  
4.  変更、**ファイバー保護の最適化を有効にする**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)