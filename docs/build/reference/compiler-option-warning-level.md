---
title: "-w、-W0、-W1、W2、-W3、W4、-、w1-w2、-w3、-w4、-壁、-wd、-お-wo、-Wv、WX (警告レベル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarningLevel
- VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarnAsError
- VC.Project.VCCLWCECompilerTool.WarnAsError
- /wx
- VC.Project.VCCLWCECompilerTool.WarningLevel
- /wall
- VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors
- /Wv
- /w0
- /w1
- /w2
- /w3
- /w4
- /wd
- /we
- /wo
dev_langs: C++
helpviewer_keywords:
- /W1 compiler option [C++]
- w compiler option [C++]
- -wo compiler option [C++]
- Warning Level compiler option
- W1 compiler option [C++]
- -we compiler option [C++]
- /WX compiler option [C++]
- -wd compiler option [C++]
- WX compiler option [C++]
- wo compiler option [C++]
- Wall compiler option [C++]
- /w compiler option
- W2 compiler option [C++]
- -W2 compiler option [C++]
- wd compiler option [C++]
- /we compiler option [C++]
- we compiler option [C++]
- -W1 compiler option [C++]
- -W4 compiler option [C++]
- -Wall compiler option [C++]
- /Wall compiler option [C++]
- -W0 compiler option [C++]
- W0 compiler option [C++]
- -WX compiler option [C++]
- /wo compiler option [C++]
- W4 compiler option [C++]
- W3 compiler option [C++]
- /wd compiler option [C++]
- warnings, as errors compiler option
- /W3 compiler option [C++]
- /W0 compiler option [C++]
- /W4 compiler option [C++]
- -W3 compiler option [C++]
- -w compiler option [C++]
- /W2 compiler option [C++]
- /Wv compiler option [C++]
ms.assetid: d6bc7bf5-c754-4879-909c-8e3a67e2629f
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f38328f94fd68b3b5402d08ddb6d2bd97e3de76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/w、/W0、/W1、/W2、/W3、/W4、/w1、/w2、/w3、/w4、/Wall、/wd、//wo、/Wv、/WX (警告レベル)
コンパイラがコンパイルの警告がどのように生成するかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/w  
/W0  
/W1  
/W2  
/W3  
/W4  
/Wall  
/Wv[<version>]  
/WX  
/w1<warning>   
/w2<warning>   
/w3<warning>   
/w4<warning>   
/wd<warning>   
/we<warning>   
/wo<warning>  
```  
  
## <a name="remarks"></a>コメント  
 警告のオプションは、どのコンパイラの警告を表示し、全体のコンパイルの警告の動作を指定します。  
  
 警告のオプションおよび関連する引数は、次の表のとおりです。  
  
|オプション|説明|  
|------------|-----------------|  
|**/w**|すべてのコンパイラ警告を抑制します。|  
|**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4**|コンパイラによって生成される警告のレベルを指定します。 有効な警告レベルを 0 ~ 4 の範囲。<br /><br /> -   **/W0**すべての警告を抑制します。<br />-   **/W1**レベル 1 (重大) 警告が表示されます。 **/W1**既定の設定です。<br />-   **/W2**レベル 1 と、レベル 2 (重要) の警告が表示されます。<br />-   **/W3**レベル 1、レベル 2 とレベル 3 (実稼働品質) 警告が表示されます。<br />-   **/W4**レベルの既定でオフになっていない 4 の (情報) 警告すべてとレベル 1、レベル 2 とレベル 3 の警告が表示されます。 柔らかいのような警告を提供することのみこのオプションを使用することをお勧めします。 ただし、新しいプロジェクトの場合がありますを使用する最適な**/W4**これにより、最小限の可能な検索ハード コードの欠陥のようにすべてのコンパイルします。|  
|**/Wall**|によって表示されるすべての警告が表示されます**/W4**およびその他のすべての警告を**/W4**は含まれません: 既定で無効になっている警告など。 詳細については、次を参照してください。[コンパイラの警告ことは、既定でオフ](../../preprocessor/compiler-warnings-that-are-off-by-default.md)です。|  
|**/Wv**`:version`|新しいバージョンのコンパイラで導入された警告を抑制する`version`です。 コンパイラの古いバージョンを使用する場合、警告なしのコンパイル コードで新しい警告があるかを確認し、一時的に警告を抑制する、新しいビルド プロセスからそれらを修正するときに、このオプションを使用することができます。 省略可能なパラメーター`version`形式の`nn`[.`mm`[.`bbbbb`] 場所`nn`メジャー バージョン番号は、`mm`は省略可能なマイナー バージョン番号と`bbbbb`コンパイラの省略可能なビルド番号です。 たとえば、使用して`/Wv:17.00.00000`Visual C 2012 以降に導入された警告を抑制します。 既定では、 **/Wv**使用して、現在のコンパイラ バージョン番号と警告を抑制します。 コンパイラのバージョンによってに関する警告の抑制については、次を参照してください。[コンパイラのバージョンでのコンパイラ警告](../..//error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md)です。|  
|**/WX**|コンパイラ警告をすべてエラーとして扱います。 新しいプロジェクトを使用する場合があります**/WX**すべてのコンパイルですべての警告を解決する最小限の可能な検索ハード コードの不具合を確認します。<br /><br /> リンカーにも、 **/WX**オプション。 詳細については、「[/WX (リンカー警告をエラーとして扱う)](../../build/reference/wx-treat-linker-warnings-as-errors.md)」を参照してください。|  
|**/w1**`n`<br /><br /> **/w2**`n`<br /><br /> **/w3**`n`<br /><br /> **/w4**`n`|警告レベルで指定された警告番号を設定`n`です。 これにより、特定の警告レベルが設定されている場合は、その警告のコンパイラの動作を変更できます。 その他の警告オプションと組み合わせてこれらのオプションを使用すると、既定の Visual Studio によって提供されるものではなく、警告などの独自のコーディング標準を適用します。<br /><br /> たとえば、`/w34326`レベル 1 ではなく、レベル 3 警告として生成される C4326 をによりします。 両方を使用してコンパイルする場合、`/w34326`オプションおよび`/W2`オプション、警告 C4326 は生成されません。|  
|**/wd**`n`|指定されているコンパイラの警告を抑制`n`です。<br /><br /> たとえば、`/wd4326`コンパイラの警告 C4326 を抑制します。|  
|**/we**`n`|指定されているコンパイラの警告扱います`n`エラーとして。<br /><br /> たとえば、`/we4326`警告番号をコンパイラによってエラーとして扱う C4326 をによりします。|  
|**/wo**`n`|指定された、コンパイラ警告がレポート`n`1 回だけです。<br /><br /> たとえば、 `/wo4326` C4326 一度だけ報告されることを警告の原因が初めて検出された、コンパイラによってです。|  
  
 使用して、プリコンパイル済みヘッダーを作成するときに警告のオプションのいずれかを使用する場合、 [/Yc](../../build/reference/yc-create-precompiled-header-file.md)オプションを使用して、プリコンパイル済みヘッダーを使用する、 [/Yu](../../build/reference/yu-use-precompiled-header-file.md)オプションの設定により、同じ警告のオプションを有効にします。もう一度です。 コマンドラインで別の警告オプションを使用して、プリコンパイル済みヘッダーで設定した警告オプションをオーバーライドできます。  
  
 使用することができます、 [#pragma 警告](../../preprocessor/warning.md)されている警告のレベルを制御するディレクティブが特定のソース ファイルのコンパイル時に報告します。  
  
 Pragma 警告ディレクティブのソース コードには影響を受けませんが、 **/w**オプション。  
  
 [ビルド エラーに関するドキュメント](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)警告と警告レベルを記述し、なぜ特定のステートメントはコンパイルされません意図どおりを示します。  
  
### <a name="to-set-the-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択**C/C++**です。  
  
3.  **全般**プロパティ ページで、変更、**警告レベル**または**警告をエラーとして扱う**プロパティです。  
  
4.  **詳細**プロパティ ページで、変更、**特定の警告を無効にする**プロパティです。  
  
5.  残りのオプションで、**コマンド ライン**プロパティ ページにコンパイラ オプションを入力、**追加オプション**ボックス。  
  
### <a name="to-set-the-compiler-option-programmatically"></a>コンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>」、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>」、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A>」、および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)