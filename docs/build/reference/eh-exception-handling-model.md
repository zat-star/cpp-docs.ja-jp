---
title: "/EH (例外処理モデル) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.ExceptionHandling"
  - "/eh"
  - "VC.Project.VCCLCompilerTool.ExceptionHandling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "例外処理、コンパイラ モデル"
  - "cl.exe コンパイラ、例外処理"
  - "EH コンパイラ オプション [C++]"
  - "-EH コンパイラ オプション [C++]"
  - "/EH コンパイラ オプション [C++]"
ms.assetid: 754b916f-d206-4472-b55a-b6f1b0f2cb4d
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# /EH (例外処理モデル)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラで使用される例外処理の種類、例外チェックを最適化して除去するタイミング、および例外が原因でスコープを外れた C\+\+ オブジェクトを破棄するかどうかを指定します。**\/EH** が指定されていない場合、コンパイラは非同期構造化例外と C\+\+ 例外の両方をキャッチしますが、非同期例外の結果としてスコープを外れた C\+\+ オブジェクトを破棄しません。  
  
## 構文  
  
```  
/EH{s|a}[c][r][-]  
```  
  
## 引数  
 **a**  
 非同期 \(構造化\) 例外と同期 \(C\+\+\) 例外の両方をキャッチする例外処理モデル。  
  
 **s**  
 C\+\+ 例外のみをキャッチし、`extern "C"` として宣言された関数が例外をスローする可能性があるものと想定するようにコンパイラに指示する例外処理モデル。  
  
 **c**  
 **s** \(**\/EHsc**\) と共に使用すると、C\+\+ 例外のみをキャッチし、`extern "C"` として宣言された関数が C\+\+ 例外をスローしないものと想定するようにコンパイラに指示します。  
  
 **\/EHca** は **\/EHa** と同じです。  
  
 **r**  
 すべての `noexcept` 関数のランタイム終了チェックを常に生成するようにコンパイラに指示します。 既定では、コンパイラが、関数がスローしない関数のみを呼び出すと判断した場合に、`noexcept` のランタイム チェックが最適化され、除去されます。  
  
## 解説  
 **\/EHa** コンパイラ オプションは、ネイティブ C\+\+ `catch(...)` 句で非同期構造化例外処理 \(SEH\) をサポートするために使用されます。**\/EHa** を指定せずに SEH を実装するために、`__try`、`__except`、`__finally` の各構文を使用する場合があります。 Windows および Visual C\+\+ は SEH をサポートしていますが、ISO 標準の C\+\+ 例外処理 \(**\/EHs** または **\/EHsc**\) の方がコードの移植性と柔軟性に優れているため、こちらの例外処理を使用することを強くお勧めします。 そうは言うものの、既存のコードや、特定の種類のプログラム、たとえば共通言語ランタイム \([\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)\) をサポートするようにコンパイルされたコードなどでは、やはり SEH を使用しなければならないことがあります。 詳細については、「[構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md)」を参照してください。  
  
 **\/EHa** を指定し、`catch(...)` を使用してすべての例外を処理しようとするのは危険です。 非同期例外のほとんどが回復不能で、致命的であると見なされます。 こうした例外をキャッチして操作を続行すると、プロセスが破損し、検出して修正するのが難しいバグが発生する可能性があります。  
  
 **\/EHs** または **\/EHsc** を使用すると、`catch(...)` 句では非同期構造化例外がキャッチされません。 アクセス違反およびマネージ <xref:System.Exception?displayProperty=fullName> 例外がキャッチされず、非同期例外が処理される場合も含め、非同期例外が生成されたときに、スコープ内のオブジェクトが破棄されることはありません。  
  
 **\/EHa** を使用すると、コンパイラが `try` ブロックを積極的に最適化しないために、イメージの容量が増えてパフォーマンスが低下する可能性があります。 また、コンパイラが C\+\+ 例外をスローする可能性のあるコードを確認しない場合でも、すべてのローカル オブジェクトのデストラクターを自動的に呼び出す例外フィルターが除去されません。 これにより、非同期例外および C\+\+ 例外のセーフ スタック アンワインドが可能になります。**\/EHs** を使用した場合は、コンパイラが `throw` ステートメントまたは関数呼び出しでしか例外が発生しないと見なします。 これにより、アンワインド可能オブジェクトの有効期間を管理するコードを削除できるため、コード サイズをかなり小さくできます。  
  
 **\/EHa** を使用してコンパイルされたオブジェクトと、**\/EHs** を使用してコンパイルされたオブジェクトを、同じ実行可能モジュールでリンクさせることはお勧めできません。 モジュールの任意の場所で **\/EHa** を使用して、非同期例外を処理する必要がある場合は、**\/EHa** を使用して、モジュール内のすべてのコードをコンパイルします。 構造化例外処理の構文は、**\/EHs** を使用してコンパイルされたコードと同じモジュールで使用できますが、この SEH 構文と、`try`、`throw`、および `catch` を同じ関数に混在させることはできません。  
  
 **\/EHa** 以外の方法で発生する例外をキャッチする場合は、`throw` を使用します。 この例では、構造化例外が生成され、キャッチされます。  
  
```  
// compiler_options_EHA.cpp // compile with: /EHa #include <iostream> #include <excpt.h> using namespace std; void fail() {   // generates SE and attempts to catch it using catch(...) try { int i = 0, j = 1; j /= i;   // This will throw a SE (divide by zero). printf("%d", j); } catch(...) {   // catch block will only be executed under /EHa cout<<"Caught an exception in catch(...)."<<endl; } } int main() { __try { fail(); } // __except will only catch an exception here __except(EXCEPTION_EXECUTE_HANDLER) { // if the exception was not caught by the catch(...) inside fail() cout << "An exception was caught in __except." << endl; } }  
```  
  
 **\/EHc** オプションでは、**\/EHs** または **\/EHa** を指定する必要があります。**\/clr** を使用すると、**\/EHa** が暗黙的に指定されます \(つまり、**\/clr \/EHa** が冗長になります\)。**\/EHs\[c\]** を **\/clr** の後で使用すると、コンパイラはエラーを生成します。 最適化処理は、この動作に影響しません。 例外がキャッチされると、例外オブジェクトまたは例外と同じスコープ内にあるオブジェクトに対して、コンパイラが 1 つまたは複数のクラス デストラクターを呼び出します。 例外がキャッチされない場合は、これらのデストラクターは実行されません。  
  
 **\/clr** に基づく例外処理の制約については、「[\_set\_se\_translator](../../c-runtime-library/reference/set-se-translator.md)」を参照してください。  
  
 マイナス記号 \(**\-**\) を使用すると、このオプションをクリアできます。 たとえば、**\/EHsc\-** は **\/EHs \/EHc\-** と解釈され、**\/EHs** と等価です。  
  
 **\/EHr** コンパイラ オプションは、`noexcept` 属性を持つすべての関数でのランタイム終了チェックを強制します。 既定では、コンパイラがバックエンドで関数が*スローしない*関数のみを呼び出すと判断した場合に、ランタイム チェックが最適化され、除去されます。 スローしない関数とは、属性で例外がスローされないことが指定された関数を指します。 これには、`noexcept`、`throw()`、`__declspec(nothrow)` とマークされた関数と、**\/EHc** が指定された場合の `extern "C"` 関数が含まれます。 スローしない関数には、コンパイラの検査でスローしないと判断された関数も含まれます。**\/EHr\-** を使用して明示的に既定に設定することができます。  
  
 ただし、スローしない属性は、関数からどの例外もスローされないことを保証するわけではありません。`noexcept` 関数の動作とは異なり、Visual C\+\+ コンパイラは、`throw()`、`__declspec(nothrow)`、または `extern "C"` を使用して宣言された関数からスローされた例外を、未定義の動作と見なします。 この 3 つの宣言属性を使用する関数は、例外のランタイム終了チェックを強制しません。`noexcept` 関数を回避する未処理例外のランタイム チェックを生成するようにコンパイラに強制することによって、**\/EHr** オプションを使用してこの未定義の動作を識別することができます。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。 詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  左ウィンドウで、**\[構成プロパティ\]**、**\[C\/C\+\+\]**、**\[コード生成\]** の順に展開します。  
  
3.  **\[C\+\+ の例外を有効にする\]** プロパティを変更します。  
  
     または、**\[C\+\+ の例外を有効にする\]** を **\[いいえ\]** に設定してから **\[コマンド ライン\]** プロパティ ページをクリックし、**\[追加のオプション\]** ボックスにコンパイラ オプションを追加します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [エラーと例外の処理](../../cpp/errors-and-exception-handling-modern-cpp.md)   
 [例外の仕様 \(スロー\)](../../cpp/exception-specifications-throw-cpp.md)   
 [構造化例外処理](../../cpp/structured-exception-handling-c-cpp.md)