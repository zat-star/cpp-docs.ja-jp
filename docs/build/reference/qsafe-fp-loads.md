---
title: "-Qsafe_fp_loads |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 2b2ce52d-ba57-4bd3-a739-47a7f8bfaba9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f79a73565a78c8972d9d77b809cd77d774b821f1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="qsafefploads"></a>/Qsafe_fp_loads
浮動小数点値の整数移動命令を要求し、特定の浮動小数点読み込み最適化を無効にします。  
  
## <a name="syntax"></a>構文  
  
```  
/Qsafe_fp_loads  
```  
  
## <a name="remarks"></a>コメント  
 **/Qsafe_fp_loads**はコンパイラでのみ使用を対象とする x86; は x64 または ARM を対象とするコンパイラで使用できません。  
  
 **/Qsafe_fp_loads**力を浮動小数点移動命令ではなく整数移動命令を使用して、メモリと MMX 間でデータを移動するコンパイラを登録します。 また、このオプションを指定すると、値の読み込み時に例外が発生する可能性がある場合 (NaN 値の読み込み時など)、複数のコントロール パスに読み込める浮動小数点値に対してレジスタ読み込み最適化が無効になります。  
  
 このオプションは、によってオーバーライド[/fp: を除く](../../build/reference/fp-specify-floating-point-behavior.md)です。 **/Qsafe_fp_loads**で指定されているコンパイラの動作のサブセットを指定**/fp: 除く**です。  
  
 **/Qsafe_fp_loads**と互換性がありません[/clr](../../build/reference/clr-common-language-runtime-compilation.md)と[/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md)です。 浮動小数点のポイント コンパイラ オプションの詳細については、次を参照してください。 [/fp (浮動小数点の動作を指定)](../../build/reference/fp-specify-floating-point-behavior.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、 **C/C++**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [/Q オプション (低水準の操作)](../../build/reference/q-options-low-level-operations.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)