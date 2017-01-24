---
title: "/clr の制約 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr コンパイラ オプション [C++], 制限事項"
ms.assetid: 385f6462-2c68-46d6-810e-469553ead447
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /clr の制約
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/clr** の使用に関する制約を次に示します。  
  
-   構造化例外ハンドラーでは、**\/clr** を指定してコンパイルする場合、`_alloca` の使用が制約されます。  詳細については、「[\_alloca](../../c-runtime-library/reference/alloca.md)」を参照してください。  
  
-   **\/clr** では、ランタイム エラー チェックを使用できません。  詳細については、「[ネイティブ ランタイム チェックの使用方法](../Topic/How%20to:%20Use%20Native%20Run-Time%20Checks.md)」を参照してください。  
  
-   C\+\+ 標準構文だけを使用するプログラムを **\/clr** を指定してコンパイルするときは、次のガイドラインがインライン アセンブリに適用されます。  
  
    -   ネイティブなスタック レイアウトや、現在の関数の外部の呼び出し規約、コンピューターに関するその他の低水準の情報の知識があることをインライン アセンブリ コードで想定し、その知識をマネージ関数のスタック フレームで利用すると、エラーが生じることがあります。  インライン アセンブリ コードが含まれた関数は、アンマネージ関数として生成され、**\/clr** を指定せずにコンパイルされた別のモジュール内に置かれた関数と同様に処理されます。  
  
    -   コピー構築された関数パラメーターを渡す関数内でのインライン アセンブリ コードの使用はサポートされません。  
  
-   **\/clr** を使ってコンパイルしたプログラムから [vprintf 関数](../../c-runtime-library/vprintf-functions.md) を呼び出すことはできません。  
  
-   [naked](../Topic/naked%20\(C++\).md) [\_\_declspec](../../cpp/declspec.md) 修飾子は、\/clr では無視されます。  
  
-   [\_set\_se\_translator](../../c-runtime-library/reference/set-se-translator.md) によって設定された変換関数は、アンマネージ コードのキャッチにだけ影響します。  詳細については、「[Exception Handling](../../windows/exception-handling-cpp-component-extensions.md)」を参照してください。  
  
-   **\/clr** では、関数ポインターを比較できません。  
  
-   **\/clr** では、完全にプロトタイプ宣言されていない関数を使用できません。  
  
-   次のコンパイル オプションは **\/clr** でサポートされていません。  
  
    -   **\/EHsc** および **\/EHs**。**\/clr** は **\/EHa** を暗黙に指定します \([\/EH \(例外処理モデル\)](../../build/reference/eh-exception-handling-model.md) を参照\)。  
  
    -   **\/fp:strict** および **\/fp:except** \([\/fp \(浮動小数点の動作の指定\)](../../build/reference/fp-specify-floating-point-behavior.md) を参照\)。  
  
    -   [\/Zd](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)  
  
    -   [\/Gm](../../build/reference/gm-enable-minimal-rebuild.md)  
  
    -   [\/MT](../../build/reference/md-mt-ld-use-run-time-library.md)  
  
    -   [\/RTC](../../build/reference/rtc-run-time-error-checks.md)  
  
    -   **\/ZI**  
  
-   `_STATIC_CPPLIB` プリプロセッサ定義 \(`/D_STATIC_CPPLIB`\) と **\/clr** または **\/clr:pure** コンパイラ オプションの組み合わせはサポートされていません。  これは、定義によってアプリケーションが、サポートされていない静的マルチスレッドの標準 C\+\+ ライブラリとリンクするためです。  詳細については、「[\/MD、\/MT、\/LD \(ランタイム ライブラリの使用\)](../../build/reference/md-mt-ld-use-run-time-library.md)」を参照してください。  
  
-   [\/J](../../build/reference/j-default-char-type-is-unsigned.md) は **\/clr:safe** および **\/clr:pure** でサポートされていません。  
  
-   ATL ライブラリと MFC ライブラリは純粋なモードのコンパイル \(**\/clr:pure**\) でサポートされていません。  **\/MD** または **\/MDd** を指定してコンパイルする場合は、C\+\+ 標準ライブラリおよび CRT で **\/clr:pure** を使用できます。  
  
-   **\/Zi** と **\/clr** を併用すると、パフォーマンスに影響を及ぼします。  詳細については、「[\/Z7、\/Zi、\/ZI \(デバッグ情報の形式\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)」を参照してください。  
  
-   ワイド文字を .NET Framework の出力ルーチンに渡すときに、[\/Zc:wchar\_t](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) を指定しなかったり、文字を `__wchar_t` にキャストしなかったりした場合、出力は `unsigned short int` として表示されます。  たとえば、次のようになります。  
  
    ```  
    Console::WriteLine(L' ')              // Will output 32.  
    Console::WriteLine((__wchar_t)L' ')   // Will output a space.  
    ```  
  
-   `#pragma`  [unmanaged](../../preprocessor/managed-unmanaged.md) で関数が指定されている場合を除いて、**\/clr** を指定すると [\/GS](../Topic/-GS%20\(Buffer%20Security%20Check\).md) は無視されます。また、関数をネイティブにコンパイルする必要がある場合は、コンパイラによって警告 C4793 が生成されますが、この警告は既定ではオフになっています。  
  
-   マネージ アプリケーションの関数シグネチャの要件については、「[\/ENTRY](../../build/reference/entry-entry-point-symbol.md)」を参照してください。  
  
-   **\/openmp** および **\/clr** を指定してコンパイルされたアプリケーションは、単一の appdomain プロセスでのみ実行できます。詳細については、「[\/openmp \(OpenMP 2.0 サポートの有効化\)](../../build/reference/openmp-enable-openmp-2-0-support.md)」を参照してください。  
  
-   可変個の引数 \(varargs\) を受け取る関数は、ネイティブ関数として生成されます。  可変個の引数位置のマネージ データ型は、ネイティブの型にマーシャリングされます。  <xref:System.String?displayProperty=fullName> 型は、実際にはワイド文字の文字列ですが、1 バイト文字の文字列にマーシャリングされます。  したがって、printf の指定子が %S \(wchar\_t\*\) の場合は、代わりに %s 文字列にマーシャリングされます。  
  
-   va\_arg マクロを使用している場合に **\/clr:pure** を指定してコンパイルを行うと、予期しない結果が発生することがあります。詳細については、「[va\_arg、va\_copy、va\_end、va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)」を参照してください。  
  
-   [異なる数の引数を処理](../Topic/Variable%20Argument%20Lists.md)するように宣言された関数に、アプリケーションが [va\_list](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) 型の引数を渡し、そのアプリケーションが **\/clr:pure** を指定してコンパイルされている場合、CLR は <xref:System.NotSupportedException> をスローします。  代わりに **\/clr**  を使用すると、影響を受ける関数はネイティブ コードにコンパイルされ、適切に実行します。  **\/clr:safe** を使用すると、エラー診断が出力されます。  
  
-   スタックを検索してパラメーター情報 \(関数の引数\) を取得する関数を、マネージ コードから呼び出さないでください。P\/Invoke レイヤーにより、取得された情報がスタックのさらに下に置かれます。たとえば、**\/clr** を指定して proxy\/stub をコンパイルしないでください。  
  
-   関数は可能な限りマネージ コードにコンパイルされますが、すべての C\+\+ 構成要素をマネージ コードに変換できるとは限りません。変換できるかどうかは関数ごとに決定されます。  関数のいずれかの部分がマネージ コードに変換できない場合は、関数全体がネイティブ コードに変換されます。  次のような場合は、マネージ コードが生成されません。  
  
    -   コンパイラが生成したサンクまたはヘルパー関数。  関数ポインターを通じたすべての関数呼び出し \(仮想関数呼び出しを含む\) に対して、ネイティブなサンクが生成されます。  
  
    -   `setjmp` または `longjmp` を呼び出す関数。  
  
    -   特定の組み込みルーチンを使用してコンピューター リソースを直接操作する関数。  たとえば、`__enable` と `__disable`、`_ReturnAddress` と `_AddressOfReturnAddress`、またはマルチメディア組み込みを使用すると、関数はすべてネイティブ コードに変換されます。  
  
    -   `#pragma unmanaged` ディレクティブの後ろにある関数。逆の `#pragma managed` もサポートされます。  
  
    -   配置される型、つまり `__declspec(align(...))` を使用して宣言された型の参照を含む関数。  
  
-   [コンパイラ COM サポート](../Topic/Compiler%20COM%20Support.md) クラスは **\/clr:pure** または **\/clr:safe** とは併用できません。  
  
## 参照  
 [\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)