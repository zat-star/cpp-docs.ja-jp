---
title: "/OPT (最適化) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.OptimizeReferences"
  - "/opt"
  - "VC.Project.VCLinkerTool.OptimizeForWindows98"
  - "VC.Project.VCLinkerTool.EnableCOMDATFolding"
  - "VC.Project.VCLinkerTool.OptimizeFolding"
  - "VC.Project.VCLinkerTool.FoldingIterations"
  - "VC.Project.VCLinkerTool.OptimizeFoldingIterations"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/OPT リンカー オプション"
  - "LINK ツール [C++], 制御 (最適化を)"
  - "リンカー [C++], 最適化"
  - "OPT リンカー オプション"
  - "-OPT リンカー オプション"
  - "最適化, リンカー"
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /OPT (最適化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK がビルド時に実行する最適化を制御します。  
  
## 構文  
  
```  
/OPT:{REF | NOREF}  
/OPT:{ICF[=iterations] | NOICF}  
/OPT:{LBR | NOLBR}  
```  
  
## 引数  
 **REF** &#124; **NOREF**  
 **\/OPT:REF** を指定すると、参照されない関数とデータが削除されます。**\/OPT:NOREF** を指定すると、参照されない関数とデータが保持されます。  
  
 \/OFT:REF を有効にすると、LINK によって、未参照のパッケージ化された関数とデータが削除されます。  オブジェクトが [\/Gy](../../build/reference/gy-enable-function-level-linking.md) オプションを使用してコンパイルされた場合、そのオブジェクトには、パッケージ化された関数とデータ \(COMDAT\) が含まれます。  この最適化は、中間 COMDAT 除去として知られています。  非デバッグ ビルドでは、**\/OPT:REF** が既定で有効になっています。  この既定の動作をオーバーライドして、参照されていない関数をそのままプログラムに残しておくには、**\/OPT:NOREF** を指定します。  特定のシンボルが除去されないようにするには、[\/INCLUDE](../../build/reference/include-force-symbol-references.md) オプションを使用します。  
  
 **\/OPT:REF** が明示的に、または既定で有効になっている場合は、**\/OPT:ICF** の制限されたフォームが有効になり、同じ関数のみが圧縮されます。  **\/OPT:REF** だけを使用して、**\/OPT:ICF** を使用しない場合は、**\/OPT:REF,NOICF** または **\/OPT:NOICF** のいずれかを指定する必要があります。  
  
 [\/DEBUG](../../build/reference/debug-generate-debug-info.md) を指定すると、**\/OPT** の既定値が **NOREF** になり、すべての関数がイメージに保存されます。  この既定値をオーバーライドしてデバッグ ビルドを最適化するには、**\/OPT:REF** を指定します。  **\/OPT:REF** が **\/OPT:ICF** を意味するため、**\/OPT:NOICF** も指定して、デバッグ ビルドで同じ関数を保持することをお勧めします。  これにより、スタック トレースを読み取って、圧縮された関数にブレークポイントを設定しやすくなります。  **\/OPT:REF** オプションを使うと、インクリメンタル リンクが行われなくなります。  
  
 `const` データが COMDAT であることを明示的に示す必要があります。[\_\_declspec\(selectany\)](../../cpp/selectany.md) で指定します。  
  
 **\/OPT:ICF** を指定しても、**\/OPT:REF** オプションは有効になりません。  
  
 **ICF\[\=**  `iterations` **\] &#124; NOICF**  
 **\/OPT:ICF\[\=** `iterations` **\]** を使用すると、同一の COMDAT が折りたたまれ \(圧縮され\) ます。  リンカー出力から余分な COMDAT シンボルを削除できます。  省略可能な `iterations` パラメーターには、シンボルの重複を検出するための走査回数を指定します。  既定値は 2 回です。  イテレーションの回数を増やすと、前回のイテレーションで圧縮されなかった重複が検出されることがあります。  
  
 **\/OPT:REF** を指定して **ICF** が既定で有効になっている場合と、**\/OPT:REF,ICF** を明示的に指定する場合とでは、リンカーの動作が異なります。  **\/OPT:REF** を指定して既定で **ICF** が有効になっている場合は、読み取り専用データが圧縮されません。これには、.rdata、.pdata、および .xdata が含まれます。  したがって、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)] のイメージを生成するときに圧縮される関数の数が少なくなります。これらのモジュールの関数は、.pdata や .xdata などの読み取り専用データへの依存性が高いためです。  **ICF** の圧縮動作を十分に活用するには、**\/OPT:ICF** を明示的に指定してください。  
  
 COMDAT に関数を配置するには、**\/Gy** コンパイラ オプションを使用します。`const` データを配置するには、`__declspec(selectany)` で宣言します。  圧縮するデータを指定する方法については、「[selectany](../../cpp/selectany.md)」を参照してください。  
  
 既定では、**REF** がオンの場合は、**ICF** もオンです。  **REF** が指定されている場合に、この既定値をオーバーライドするには、**NOICF** を使用します。  デバッグ ビルドで **\/OPT:REF** が指定されていない場合は、**\/OPT:ICF** を明示的に指定して、COMDAT 圧縮を有効にする必要があります。  ただし、**\/OPT:ICF** は、同一のデータまたは関数をマージできるため、スタック トレースに表示される関数名が変更されることがあります。  また、特定の関数にブレークポイントを設定したり、デバッガーで特定のデータを確認したりできなくなり、コードをシングル ステップ実行すると、予期しない関数が発生します。  したがって、コードを小さくする利点がこうした欠点を上回らない限り、デバッグ ビルドで **\/OPT:ICF** を使用することはお勧めしません。  
  
> [!NOTE]
>  **\/OPT:ICF** を使用すると、同じアドレスが、さまざまな関数または読み取り専用のデータ メンバー \(**\/Gy** を使用してコンパイルされた `const` 変数\) に割り当てられることがあります。このため、その関数や読み取り専用のデータ メンバーの一意のアドレスに依存するプログラムが中断される可能性があります。  詳細については、「[\/Gy \(関数レベルのリンクの有効化\)](../../build/reference/gy-enable-function-level-linking.md)」を参照してください。  
  
 **LBR** &#124; **NOLBR**  
 **\/OPT:LBR** オプションおよび **\/OPT:NOLBR** オプションは、ARM バイナリのみに適用されます。  特定の ARM プロセッサの分岐命令の範囲が限られているため、リンカーは、範囲外のアドレスへのジャンプを検出すると、分岐命令の終点アドレスを、実際の終点を対象とする分岐命令を含むコード "アイランド" のアドレスに置き換えます。  **\/OPT:LBR** を使用すると、長い分岐命令の検出と、中間コード アイランドの配置を最適化して、コード全体のサイズを最小化できます。  **\/OPT:NOLBR** は、長い分岐命令が検出されると、最適化を行わずに長い分岐命令のコード アイランドを生成するようにリンカーに指示します。  
  
 既定で、**\/OPT:LBR** オプションは、インクリメンタル リンクが有効化されていない場合に設定されます。  非インクリメンタル リンクが必要で、長い分岐命令の最適化が不要な場合は、**\/OPT:NOLBR** を指定します。  **\/OPT:LBR** オプションを使うと、インクリメンタル リンクが行われなくなります。  
  
## 解説  
 通常、最適化によってイメージのサイズが小さくなり、プログラムの実行速度が向上します。ただし、その代わりにリンク時間が長くなります。  
  
 [\/VERBOSE](../../build/reference/verbose-print-progress-messages.md) オプションを使用すると、**\/OPT:REF** によって取り除かれた関数や **\/OPT:ICF** によって折りたたまれた \(圧縮された\) 関数を表示できます。  
  
### Visual Studio 開発環境で OPT:ICF リンカー オプションまたは OPT:REF リンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  左ペインで、**\[構成プロパティ\]**、**\[リンカー\]**、**\[最適化\]** の順に展開します。  
  
3.  次のいずれかのプロパティを変更します。  
  
    -   **\[COMDAT の圧縮\]**  
  
    -   **参考文献**  
  
### Visual Studio 開発環境で OPT:LBR リンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\[追加オプション\]** にオプションを入力します。  
  
     `/opt:lbr`  
  
### このリンカーをコードから設定するには  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> プロパティを参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)