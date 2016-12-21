---
title: "/RTC (ランタイム エラー チェック) | Microsoft Docs"
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
  - "/rtc"
  - "VC.Project.VCCLCompilerTool.SmallerTypeCheck"
  - "VC.Project.VCCLCompilerTool.UninitializedVariableCheck"
  - "VC.Project.VCCLCompilerTool.StackFrameCheck"
  - "VC.Project.VCCLCompilerTool.BasicRuntimeChecks"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RTC1 コンパイラ オプション [C++]"
  - "/RTCc コンパイラ オプション [C++]"
  - "/RTCs コンパイラ オプション [C++]"
  - "/RTCu コンパイラ オプション [C++]"
  - "__MSVC_RUNTIME_CHECKS マクロ"
  - "RTC1 コンパイラ オプション"
  - "-RTC1 コンパイラ オプション [C++]"
  - "RTCc コンパイラ オプション"
  - "-RTCc コンパイラ オプション [C++]"
  - "RTCs コンパイラ オプション"
  - "-RTCs コンパイラ オプション [C++]"
  - "RTCu コンパイラ オプション"
  - "-RTCu コンパイラ オプション [C++]"
  - "ランタイム チェック, /RTC オプション"
  - "ランタイム エラー, エラー チェック"
  - "ランタイム エラー, ランタイム チェック"
ms.assetid: 9702c558-412c-4004-acd5-80761f589368
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /RTC (ランタイム エラー チェック)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ランタイム エラー チェック機能を有効または無効にするために、[runtime\_checks](../Topic/runtime_checks.md) プラグマと組み合わせて使用されます。  
  
## 構文  
  
```  
/RTC1  
/RTCc  
/RTCs  
/RTCu  
```  
  
## Arguments  
 `1`  
 **\/RTC** `su` と等価です。  
  
 `c`  
 より小さいデータ型に値が代入されてデータが失われる場合に報告します。  たとえば、`short 0x101` 型の値を `char` 型の変数に代入する場合です。  
  
 このオプションは、たとえば `int` の先頭 8 ビットを `char` 型として返す場合のように、切り捨てを予定している場合に報告します。  代入の結果、情報が失われる場合は、**\/RTC**`c` によってランタイム エラーが生じます。**\/RTC**`c` がランタイム エラーを起こさないようにするには、必要な情報にマスクを設定します。  たとえば、次のようになります。  
  
```  
#include <crtdbg.h>  
  
char get8bits(int value, int position) {  
   _ASSERT(position < 32);  
   return (char)(value >> position);  
   // Try the following line instead:  
   // return (char)((value >> position) & 0xff);  
}  
  
int main() {  
   get8bits(12341235,3);  
}  
```  
  
 `s`  
 スタック フレームのランタイム エラー チェックを次のようにして有効にします。  
  
-   ローカル変数をゼロ以外の値に初期化します。  これはデバッグ モードでの実行中に出現しないバグを識別するのに役立ちます。  リリース ビルドでは、スタック変数のコンパイラ最適化が指定されているため、デバッグ ビルドではリリース ビルドよりもスタック変数がゼロに設定されたままになっている可能性が高くなります。  いったんスタックの領域がプログラムによって使用されると、コンパイラによって 0 にリセットされることはありません。  したがって、後続の初期化されていないスタック変数が同じスタック領域を使用すると、前回のスタック メモリの使用から残されていた値が返される可能性があります。  
  
-   配列などのローカル変数のオーバーランとアンダーランを検出します。  コンパイラによって構造体に埋め込まれたメモリにアクセスしたときは、**\/RTC**`s` はオーバーランを検出しません。  埋め込みは、[align](../../cpp/align-cpp.md)、[\/Zp \(構造体メンバーの配置\)](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md)、または [pack](../../preprocessor/pack.md) を使用した場合、または埋め込みを追加しなければならないような方法で構造体の要素を要求した場合に起こります。  
  
-   スタック ポインターの検証によって、スタック ポインターの破損を検出します。  呼び出し規約の不一致によって、スタック ポインターが破損することがあります。  たとえば、関数のポインターを [\_\_cdecl](../Topic/__cdecl.md) として宣言したが、関数ポインターを使用して [\_\_stdcall](../../cpp/stdcall.md) としてエクスポートされた DLL の関数を呼び出した場合です。  
  
 `u`  
 初期化されていない変数を使用したときに報告します。  たとえば、ある命令で `C4701` が生成されると、**\/RTC**`u` でランタイム エラーが生成されることがあります。  [コンパイラの警告 \(レベル 1 およびレベル 4\) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) を生成した命令はすべて **\/RTC**`u` でランタイム エラーを生成します。  
  
 ただし、次のコードのような場合もあります。  
  
```  
int a, *b, c;  
if ( 1 )  
b = &a;  
c = a;  // No run-time error with /RTCu  
```  
  
 変数が初期化された場合、**\/RTC**`u` からランタイム エラーは報告されません。  たとえば、ポインターを使って変数にエイリアスが設定されている場合、コンパイラは変数を追跡しないため、変数が初期化されずに使用されても報告しません。  事実上、変数のアドレスを取ることで、その変数を初期化できます。  & 演算子は代入演算子のようにこの場合です。  
  
## 解説  
 ランタイム エラー チェックは、実行中のコードの問題を見つけるための方法です。詳細については、「[方法 : ネイティブ ランタイム チェックを使用する](../Topic/How%20to:%20Use%20Native%20Run-Time%20Checks.md)」を参照してください。  
  
 いずれかの **\/RTC** コンパイラ オプションを使ってコマンド ラインでプログラムをコンパイルすると、コードのすべてのプラグマ [optimize](../../preprocessor/optimize.md) 命令は失敗します。  これは、リリース \(最適化\) ビルドではランタイム エラー チェックが無効になるためです。  
  
 **\/RTC** は開発ビルドで使用する必要があります。リリース ビルドでは **\/RTC** を使用しないでください。  **\/RTC** は、コンパイラの最適化 \([\/O オプション \(コードの最適化\)](../../build/reference/o-options-optimize-code.md)\) と同時に使用することはできません。  **\/RTC** を指定してビルドされたプログラム イメージは、**\/Od** でビルドされたイメージよりもわずかに大きく、またわずかに遅くなります \(**\/Od** ビルドよりも最大 5% 遅くなります\)。  
  
 **\/RTC** オプションまたは [\/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md) を使用すると、\_\_MSVC\_RUNTIME\_CHECKS プリプロセッサ ディレクティブが定義されます。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コード生成\]** プロパティ ページをクリックします。  
  
4.  **\[基本ランタイム チェック\]** プロパティと **\[小さい型への変換チェック\]** プロパティのいずれか、または両方を変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A> プロパティを参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [RTC sample](http://msdn.microsoft.com/ja-jp/b3415b09-f6fd-43dc-8c02-9a910bc2574e)