---
title: "/fp (浮動小数点の動作の指定) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.floatingPointModel"
  - "VC.Project.VCCLWCECompilerTool.FloatingPointExceptions"
  - "/fp"
  - "VC.Project.VCCLWCECompilerTool.floatingPointModel"
  - "VC.Project.VCCLCompilerTool.FloatingPointExceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/fp コンパイラ オプション [C++]"
  - "-fp コンパイラ オプション [C++]"
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# /fp (浮動小数点の動作の指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ソース コード ファイルの浮動小数点の動作を指定します。  
  
## 構文  
  
```  
/fp:[precise | except[-] | fast | strict ]  
```  
  
## フラグ  
 **precise**  
 これが既定値です。  
  
 浮動小数点演算の精度に影響する最適化処理を無効にし、演算結果が一致するかどうかを判定する浮動小数点テストの一貫性を向上させます \(ANSI 基準に厳密に従うには、特定の精度を保持する必要があります\)。既定では、x86 アーキテクチャのコードでは、浮動小数点演算の中間結果は、コプロセッサの 80 ビット レジスタに保持されます。  これにより、プログラムの実行速度が向上し、プログラムのサイズも小さくなります。  ただし、浮動小数点演算では、80 ビット未満のメモリで表される浮動小数点データ型も使用されるため、処理内容の多い演算では、このように余分な精度ビット、つまり、80 ビットと実際の浮動小数点データ型のビット数との差があると、演算結果の一貫性が失われることがあります。  
  
 x86 プロセッサの **\/fp:precise** では、パラメーターが関数に渡されるときに、コンパイラは `float` 型の変数を正しい有効桁数に丸め、割り当ておよびキャストが適切に行われるようにします。  この丸めにより、データが型の容量を大幅に上回らないようにします。  **\/fp:precise** でコンパイルされたプログラムは、**\/fp:precise** を使用せずにコンパイルされたプログラムよりも処理速度が遅く、サイズも大きくなります。  **\/fp:precise** は組み込みを無効にするため、代わりに標準のランタイム ライブラリ ルーチンが使用されます。  詳細については、「[\/Oi \(組み込み関数の生成\)](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md)」を参照してください。  
  
 次の浮動小数点の動作は **\/fp:precise** で有効にします。  
  
-   短縮操作、つまり、最後に 1 回だけ丸め処理を行う複合演算を使用して、複数の演算を置き換える操作。  
  
-   特殊な値 \(NaN、\+infinity、\-infinity、\+0、\-0\) に対して無効な式の最適化は使用できません。  最適化 x\-x \=\> 0、x\*0 \=\> 0、x\-0 \=\> x、x\+0 \=\> x、および 0\-x \=\> \-x は、さまざまな理由によりすべて無効です \(詳細については、IEEE 754 および C99 標準を参照してください\)。  
  
-   コンパイラは、NaN が含まれている比較を適切に処理します。  たとえば、`x` が NaN の場合、x \!\= x は **true** になり、NaN が含まれている順序比較では例外が発生します。  
  
-   式の評価は C99 FLT\_EVAL\_METHOD\=2 に従いますが、1 つだけ例外があります。x86 プロセッサに対するプログラミングでは、FPU は 53 ビット精度に設定されるため、long double 精度と見なされます。  
  
-   厳密な 1.0 での乗算では他の係数に変換されます。  たとえば、x\*y\*1.0 は x\*y になります。  同じように、x\*1.0\*y は x\*y になります。  
  
-   厳密な 1.0 での除算では被除数が使用されます。  たとえば、x\*y\/1.0 は x\*y になります。  同じように、x\/1.0\*y は x\*y になります。  
  
 [fenv\_access](../../preprocessor/fenv-access.md) がオンのときに **\/fp:precise** を使用すると、浮動小数点式のコンパイル時間の評価などの一部の最適化が無効になります。  たとえば、[\_control87、\_controlfp、\_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md) を使用して丸めモードを変更した場合、コンパイラは浮動小数点を計算しますが、指定した丸めモードは `fenv_access` がオンになるまでは無効です。  
  
 **\/fp:precise** は **\/Op** コンパイラ オプションを置き換えます。  
  
 **fast**  
 浮動小数点演算を最適化するため規則を緩和することで、ほとんどの場合、最高速のコードを作成します。  これにより、コンパイラは速度のために精度と正確性を犠牲にして、浮動小数点コードを最適化できます。  **\/fp:fast** が指定されると、コンパイラは代入ステートメント、型キャスト、または関数呼び出しで正しく丸め処理を行わず、中間式を丸めない可能性があります。  そして、有限の精度の結果に対する影響を考慮せずに、たとえば、結合規則および分配規則に従って、演算の順序を変更するか、代数変換を実行する可能性があります。  また、C\+\+ の型の上位変換規則に従う代わりに、演算とオペランドを単精度に変更する場合があります。  浮動小数点固有の短縮形の最適化は常に有効になります \([fp\_contract](../../preprocessor/fp-contract.md) はオンです\)。  浮動小数点の例外および FPU 環境のアクセスは無効になります \(**\/fp:except\-** が暗黙的に指定され、[fenv\_access](../../preprocessor/fenv-access.md) はオフです\)。  
  
 **\/fp:fast** は、**\/fp:strict** または **\/fp:precise** と併用できません。  コマンド ラインに指定された最後のオプションが使用されます。  **\/fp:fast** と **\/fp:except** の両方を指定すると、コンパイラ エラーが発生します。  
  
 [\/Za、\/Ze \(言語拡張機能の無効化\)](../../build/reference/za-ze-disable-language-extensions.md) \(ANSI 互換性\) と **\/fp:fast** を指定すると、予期しない動作が発生することがあります。  たとえば、単精度の浮動小数点演算が単精度に丸められない場合があります。  
  
 **except\[\-\]**  
 信頼性の高い浮動小数点例外モデル。  例外は発生直後にスローされます。  このオプションの既定値はオフです。  オプションにマイナス記号を付けると、オプションは明示的に無効になります。  
  
 **strict**  
 厳密な浮動小数点モデル。  **\/fp:strict** は [fp\_contract](../../preprocessor/fp-contract.md) を OFF にし、[fenv\_access](../../preprocessor/fenv-access.md) を ON にします。  **\/fp:except** は暗黙に指定され、**\/fp:except\-** を指定して明示的に無効にできます。  **\/fp:except\-** を使用する場合、**\/fp:strict** は厳密な浮動小数点のセマンティクスを適用しますが、例外イベントは無視します。  
  
## 解説  
 1 つのコンパイルで複数の **\/fp** オプションを指定できます。  
  
 浮動小数点の動作を関数で制御するには、「[float\_control](../Topic/float_control.md) プラグマ」を参照してください。  これにより、**\/fp** コンパイラの設定がオーバーライドされます。  優れたエンジニアリング手法として、ローカル浮動小数点の動作を保存して、元に戻すことをお勧めします。  
  
```css  
#pragma float_control(precise, on, push)  
// Code that uses /fp:precise mode  
#pragma float_control(pop)  
```  
  
 浮動小数点の最適化のほとんどは **\/fp:strict**、**\/fp:except**、およびそれに対応するプラグマに関連しており、`fp_contract` プラグマはマシンに依存しています。  **\/fp:strict** と **\/fp:except** は **\/clr** と互換性がありません。  
  
 **\/fp:precise** は、アプリケーションのほとんどの浮動小数点要件に対応します。  **\/fp:except** および **\/fp:strict** を使用できますが、パフォーマンスが低下する場合があります。  パフォーマンスが最も重要である場合は、**\/fp:fast** を使用することを検討してください。  
  
 **\/fp:strict**、**\/fp:fast**、および **\/fp:precise** は精密 \(正確\) なモードです。  一度に 1 つのモードだけを使用できます。  **\/fp:strict** と **\/fp:precise** の両方が指定されている場合、コンパイラは最後に処理した方を使用します。  **\/fp:strict** と **\/fp:fast** の両方を指定することはできません。  
  
 詳細については、「[Microsoft Visual C\+\+ Floating\-Point Optimization \(Microsoft Visual C\+\+ での浮動小数点の最適化\)](http://msdn.microsoft.com/library/aa289157.aspx)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[C\/C\+\+\]** ノードを展開します。  
  
4.  **\[コード生成\]** プロパティ ページを選択します。  
  
5.  **\[浮動小数点モデル\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [Microsoft Visual C\+\+ Floating Point Optimization \(Microsoft Visual C\+\+ 浮動小数点の最適化\)](http://msdn.microsoft.com/library/aa289157.aspx)