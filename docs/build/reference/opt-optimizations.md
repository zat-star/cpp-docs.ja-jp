---
title: -OPT (最適化) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 928968803dc008eb39b3d0c52152c1f3b631a852
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="opt-optimizations"></a>/OPT (最適化)
LINK がビルド時に実行する最適化を制御します。  
  
## <a name="syntax"></a>構文  
  
```  
/OPT:{REF | NOREF}  
/OPT:{ICF[=iterations] | NOICF}  
/OPT:{LBR | NOLBR}  
```  
  
## <a name="arguments"></a>引数  
 **REF** &AMP;#124; **NOREF**  
 **/Opt:ref による**排除関数とデータが参照されていません。**/OPT:NOREF**関数および参照されないデータを保持します。  
  
 /Opt:ref によるを有効にすると、リンクは、未参照のパッケージ化された関数とデータを削除します。 オブジェクトを含むパッケージ化された関数とデータ (Comdat) を使用してコンパイルされた場合、 [/Gy](../../build/reference/gy-enable-function-level-linking.md)オプション。 この最適化は、中間 COMDAT 除去として知られています。 既定では、 **/opt:ref による**非デバッグ ビルドで有効にします。 プログラムで参照されていない Comdat を変更この既定値を上書きするには、次のように指定します。 **/OPT:NOREF**です。 使用することができます、 [/include](../../build/reference/include-force-symbol-references.md)シンボルの特定の削除のオーバーライド オプションを指定します。  
  
 ときに**/opt:ref による**明示的にまたは、既定の制限されたフォームで有効になって**/OPT:ICF**が有効になっている同じ関数なりのみが圧縮されます。 場合は**/opt:ref による**ではなく**/OPT:ICF**、どちらかを指定する必要があります**/opt:ref による、NOICF**または**/OPT:NOICF**です。  
  
 場合[/debug](../../build/reference/debug-generate-debug-info.md)が指定されているの既定の**/opt**は**NOREF**、され、イメージのすべての機能が保持されます。 この既定の動作をオーバーライドし、デバッグ ビルドを最適化するには指定**/opt:ref による**です。 **/Opt:ref による**意味**/OPT:ICF**も指定することをお勧め**/OPT:NOICF**デバッグ ビルドで同じ関数を保持します。 これにより、スタック トレースを読み取って、圧縮された関数にブレークポイントを設定しやすくなります。 **/Opt:ref による**オプションは、インクリメンタル リンクを無効になります。  
  
 明示的にマークする必要がある`const`データが COMDAT; 使用して[__declspec(selectany)](../../cpp/selectany.md)です。  
  
 指定する**/OPT:ICF**が有効にしません、 **/opt:ref による**オプション。  
  
 **ICF [=** `iterations` **] &AMP;#124; NOICF**   
 使用して**/OPT:ICF [=**`iterations`**]**を同一の COMDAT の圧縮を実行します。 リンカー出力から余分な COMDAT シンボルを削除できます。 省略可能な `iterations` パラメーターには、シンボルの重複を検出するための走査回数を指定します。 既定値は 2 回です。 イテレーションの回数を増やすと、前回のイテレーションで圧縮されなかった重複が検出されることがあります。  
  
 リンカーの動作が異なるときに**/opt:ref による**が指定されている — と**ICF**が既定で有効で — 場合よりも**/opt:ref による、ICF**が明示的に指定します。 フォーム**ICF**に対応した**/opt:ref による**単独で読み取り専用のデータはたたみ込まれません、これには、.rdata、.pdata、および .xdata が含まれます。 したがって、[!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] のイメージを生成するときに圧縮される関数の数が少なくなります。これらのモジュールの関数は、.pdata や .xdata などの読み取り専用データへの依存性が高いためです。 十分に活用する**ICF**圧縮動作を明示的に指定して**/OPT:ICF**です。  
  
 使用する関数に配置する Comdat、 **/Gy**を配置する; コンパイラ オプション`const`宣言するデータ、`__declspec(selectany)`です。 データ圧縮を指定する方法については、次を参照してください。 [selectany](../../cpp/selectany.md)です。  
  
 既定では、 **ICF**がオンの場合**REF**にします。 場合に、この既定の動作をオーバーライドする**REF**が使用して指定すると、 **NOICF**です。 ときに**/opt:ref による**が指定されていないデバッグ ビルドで明示的に指定する必要があります**/OPT:ICF** COMDAT の圧縮を有効にします。 ただし、ため**/OPT:ICF**同一のデータまたは関数をマージすることができます、スタック トレースに表示される関数名を変更することができます。 また、特定の関数にブレークポイントを設定したり、デバッガーで特定のデータを確認したりできなくなり、コードをシングル ステップ実行すると、予期しない関数が発生します。 そのため、おしないで使用する**/OPT:ICF**デバッグ ビルドでより小さなコードの利点がこうした欠点を上回らない限り、します。  
  
> [!NOTE]
>  **/OPT:ICF**同じアドレスを別の関数または読み取り専用のデータ メンバーに割り当てられる可能性があります (`const`変数を使用してコンパイル**/Gy**)、それに依存しているプログラムが中断されることができます関数または読み取り専用データ メンバーの一意のアドレス。 詳細については、「[/Gy (関数レベルのリンクの有効化)](../../build/reference/gy-enable-function-level-linking.md)」を参照してください。  
  
 **LBR** &AMP;#124; **NOLBR**  
 **/OPT:LBR**と**/OPT:NOLBR**オプションは、ARM バイナリのみに適用します。 特定の ARM プロセッサの分岐命令の範囲が限られているため、リンカーは、範囲外のアドレスへのジャンプを検出すると、分岐命令の終点アドレスを、実際の終点を対象とする分岐命令を含むコード "アイランド" のアドレスに置き換えます。 使用することができます**/OPT:LBR**長い分岐命令の検出と、コード全体のサイズを最小限に抑える中間コード アイランドの配置を最適化します。 **/OPT:NOLBR**が検出されると、最適化を行わずに長い分岐命令のコード アイランドを生成するようにリンカーに指示します。  
  
 既定では、 **/OPT:LBR**インクリメンタル リンクが有効でない場合に、オプションが設定されています。 非インクリメンタル リンクですがない時間の長い分岐命令の最適化をする場合、指定**/OPT:NOLBR**です。 **/OPT:LBR**オプションは、インクリメンタル リンクを無効になります。  
  
## <a name="remarks"></a>コメント  
 通常、最適化によってイメージのサイズが小さくなり、プログラムの実行速度が向上します。ただし、その代わりにリンク時間が長くなります。  
  
 使用することができます、 [/verbose](../../build/reference/verbose-print-progress-messages.md)によって削除された関数を参照するにはオプション**/opt:ref による**およびによって圧縮された関数**/OPT:ICF**です。  
  
### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で OPT:ICF リンカー オプションまたは OPT:REF リンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  左側のウィンドウで展開**構成プロパティ**、**リンカー**、**最適化**です。  
  
3.  次のいずれかのプロパティを変更します。  
  
    -   **COMDAT の圧縮**  
  
    -   **参照**  
  
### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で OPT:LBR リンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**リンカー**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  オプションを入力して**追加オプション**:  
  
     `/opt:lbr`  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> プロパティを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)
