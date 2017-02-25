---
title: "定義済みマクロ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_VER"
  - "__ATOM__"
  - "__AVX__"
  - "__AVX2__"
  - "_CHAR_UNSIGNED"
  - "__CLR_VER"
  - "_CONTROL_FLOW_GUARD"
  - "__COUNTER__"
  - "__cplusplus"
  - "__cplusplus_cli"
  - "__cplusplus_winrt"
  - "_CPPRTTI"
  - "_CPPUNWIND"
  - "__DATE__"
  - "_DEBUG"
  - "_DLL"
  - "__FILE__"
  - "__FUNCDNAME__"
  - "__FUNCSIG__"
  - "__FUNCTION__"
  - "_INTEGRAL_MAX_BITS"
  - "_ISO_VOLATILE"
  - "_KERNEL_MODE"
  - "__LINE__"
  - "_M_AMD64"
  - "_M_ARM"
  - "_M_ARM_ARMV7VE"
  - "_M_ARM_FP"
  - "_M_ARM64"
  - "_M_CEE"
  - "_M_CEE_PURE"
  - "_M_CEE_SAFE"
  - "_M_FP_EXCEPT"
  - "_M_FP_FAST"
  - "_M_FP_PRECISE"
  - "_M_FP_STRICT"
  - "_M_IX86"
  - "_M_IX86_FP"
  - "_M_X64"
  - "_MANAGED"
  - "_MFC_VER"
  - "_MSC_BUILD"
  - "_MSC_EXTENSIONS"
  - "_MSC_FULL_VER"
  - "_MSC_VER"
  - "_MSVC_LANG"
  - "__MSVC_RUNTIME_CHECKS"
  - "_MT"
  - "_NATIVE_WCHAR_T_DEFINED"
  - "_NO_SIZED_DEALLOCATION"
  - "_OPENMP"
  - "_PREFAST_"
  - "_RESUMABLE_FUNCTIONS_SUPPORTED"
  - "_RTC_CONVERSION_CHECKS_ENABLED"
  - "__STDC__"
  - "__STDC_HOSTED__"
  - "__STDCPP_THREADS__"
  - "__TIME__"
  - "__TIMESTAMP__"
  - "__VA_ARGS__"
  - "_VC_NODEFAULTLIB"
  - "_WCHAR_T_DEFINED"
  - "_WIN32"
  - "_WIN64"
  - "_WINRT_DLL"
  - "__func__"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "タイムスタンプ、プリプロセッサ マクロ"
  - "cl.exe コンパイラ、バージョン番号"
  - "バージョン番号は、C/C++ コンパイラ (cl.exe)"
  - "定義済みの C++ のマクロ"
  - "プリプロセッサ マクロ"
  - "定義済みマクロ"
  - "_ATL_VER マクロ"
  - "__ATOM__ マクロ"
  - "__AVX__ マクロ"
  - "__AVX2__ マクロ"
  - "_CHAR_UNSIGNED マクロ"
  - "__CLR_VER マクロ"
  - "_CONTROL_FLOW_GUARD マクロ"
  - "__COUNTER__ マクロ"
  - "__cplusplus マクロ"
  - "__cplusplus_cli マクロ"
  - "__cplusplus_winrt マクロ"
  - "_CPPRTTI マクロ"
  - "_CPPUNWIND マクロ"
  - "__DATE__ マクロ"
  - "_DEBUG マクロ"
  - "_DLL マクロ"
  - "__FILE__ マクロ"
  - "__FUNCDNAME__ マクロ"
  - "__FUNCSIG__ マクロ"
  - "__FUNCTION__ マクロ"
  - "_INTEGRAL_MAX_BITS マクロ"
  - "_ISO_VOLATILE マクロ"
  - "_KERNEL_MODE マクロ"
  - "__LINE__ マクロ"
  - "_M_AMD64 マクロ"
  - "_M_ARM マクロ"
  - "_M_ARM_ARMV7VE マクロ"
  - "_M_ARM_FP マクロ"
  - "_M_ARM64 マクロ"
  - "_M_CEE マクロ"
  - "_M_CEE_PURE マクロ"
  - "_M_CEE_SAFE マクロ"
  - "_M_FP_EXCEPT マクロ"
  - "_M_FP_FAST マクロ"
  - "_M_FP_PRECISE マクロ"
  - "_M_FP_STRICT マクロ"
  - "_M_IX86 マクロ"
  - "_M_IX86_FP マクロ"
  - "_M_X64 マクロ"
  - "_MANAGED マクロ"
  - "_MFC_VER マクロ"
  - "_MSC_BUILD マクロ"
  - "_MSC_EXTENSIONS マクロ"
  - "_MSC_FULL_VER マクロ"
  - "_MSC_VER マクロ"
  - "_MSVC_LANG マクロ"
  - "__MSVC_RUNTIME_CHECKS マクロ"
  - "_MT マクロ"
  - "_NATIVE_WCHAR_T_DEFINED マクロ"
  - "_NO_SIZED_DEALLOCATION マクロ"
  - "_OPENMP マクロ"
  - "_PREFAST_ マクロ"
  - "_RESUMABLE_FUNCTIONS_SUPPORTED マクロ"
  - "_RTC_CONVERSION_CHECKS_ENABLED マクロ"
  - "__STDC__ マクロ"
  - "__STDC_HOSTED__ マクロ"
  - "__STDCPP_THREADS__ マクロ"
  - "__TIME__ マクロ"
  - "__TIMESTAMP__ マクロ"
  - "_ _Va_args _ _ マクロ"
  - "_VC_NODEFAULTLIB マクロ"
  - "_WCHAR_T_DEFINED マクロ"
  - "_WIN32 マクロ"
  - "_WIN64 マクロ"
  - "_WINRT_DLL マクロ"
  - "_ _func _ _ の識別子"
ms.assetid: 1cc5f70a-a225-469c-aed0-fe766238e23f
caps.latest.revision: 75
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 75
---
# 定義済みマクロ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C コンパイラは言語 (C または C++)、対象をコンパイルおよび選択したコンパイラ オプションによって、特定のプリプロセッサ マクロが組み込まれています。  
  
 Visual C には、ANSI/ISO C99 標準および ISO の c++ 14 標準で指定された必須の定義済みプリプロセッサ マクロがサポートしています。 実装では、その他のいくつかの Microsoft 固有の仕様プリプロセッサ マクロもサポートします。 いくつかのマクロは、特定のビルド環境、またはコンパイラ オプションののみ定義されます。 として指定された場合と、翻訳単位全体でのマクロが定義されて、記載がなければ **/D** コンパイラ オプションの引数。 定義した場合、マクロは、コンパイル前にプリプロセッサによって指定された値に拡張されます。 定義済みマクロは引数を取らずし、再定義することはできません。  
  
## <a name="standard-predefined-identifier"></a>標準の定義済み識別子  
 コンパイラは、ISO C99 および c++ 11 で指定されたこの事前定義の識別子をサポートします。  
  
-   **__func\_\_** 関数 local として外側の関数の非修飾かつ名前 `static``const` の配列 `char`します。  
  
    ```cpp  
    void example(){  
        printf("%s\n", __func__);  
    } // prints "example"  
    ```  
  
## <a name="standard-predefined-macros"></a>標準の定義済みマクロ  
 コンパイラは、ISO C99 および ISO c++ 14 標準で指定されたこれらの定義済みマクロをサポートします。  
  
-   **_ _cplusplus** 翻訳単位が C++ としてコンパイルするときに、整数リテラル値として定義します。 それ以外の場合、定義されていません。  
  
-   **__DATE\_\_** 現在のソース ファイルのコンパイル日付。 日付が固定長の文字列形式のリテラル *Mmm dd yyyy*します。 月の名前 *Mmm* C ランタイム ライブラリによって生成される日付の月の省略名と同じは [asctime](../c-runtime-library/reference/asctime-wasctime.md) 関数です。 日付の最初の文字 *dd* スペースは、値が 10 未満である場合。 このマクロは、常に定義されます。  
  
-   **__FILE\_\_** 現在のソース ファイルの名前。 **__FILE\_\_** 文字の文字列リテラルに展開します。 ファイルへの完全パスが表示されることを確認するには使用 [/FC (完全パスのソース コード ファイルで診断)](../Topic/-FC%20\(Full%20Path%20of%20Source%20Code%20File%20in%20Diagnostics\).md)します。 このマクロは、常に定義されます。  
  
-   **__LINE\_\_** 現在のソース ファイル内の整数の行番号として定義します。 値、 **__LINE\_\_** マクロを使用して変更することができます、 `#line` ディレクティブです。 このマクロは、常に定義されます。  
  
-   **__STDC\_\_** C としてコンパイルされた場合、および 1 として定義されている、 [/Za](../build/reference/za-ze-disable-language-extensions.md) コンパイラ オプションを指定します。 それ以外の場合、定義されていません。  
  
-   **__STDC_HOSTED\_\_** 実装がある場合は、1 として定義されている、 *実装がホストされている*, 、必要な標準ライブラリ全体をサポートしています。 それ以外の場合、0 として定義されます。  
  
-   **__STDCPP_THREADS\_\_** プログラムが、実行の 1 つ以上のスレッドを持つ場合に限り、1 として定義されており、C++ としてコンパイルします。 それ以外の場合、定義されていません。  
  
-   **__TIME\_\_** 前処理された翻訳単位の変換のときです。 時間は、文字の文字列形式のリテラル *hh:mm:ss*, 、C ランタイム ライブラリによって返されるときと同じ [asctime](../c-runtime-library/reference/asctime-wasctime.md) 関数です。 このマクロは、常に定義されます。  
  
## <a name="microsoft-specific-predefined-macros"></a>Microsoft 固有の定義済みマクロ  
 Microsoft Visual C には、これらの追加の定義済みマクロがサポートしています。  
  
-   **__ATOM\_\_** 場合に 1 として定義されている、 [/favor:ATOM](../build/reference/favor-optimize-for-architecture-specifics.md) コンパイラ オプションが設定され、コンパイラのターゲットは、x86 または x64。 それ以外の場合、定義されていません。  
  
-   **__AVX\_\_** 場合に 1 として定義されている、 [/arch:AVX](../build/reference/arch-x86.md) または [/arch:AVX2](../build/reference/arch-x86.md) コンパイラ オプションを設定し、コンパイラのターゲットは、x86 または x64。 それ以外の場合、定義されていません。  
  
-   **__AVX2\_\_** 場合に 1 として定義されている、 [/arch:AVX2](../build/reference/arch-x86.md) コンパイラ オプションが設定され、コンパイラのターゲットは、x86 または x64。 それ以外の場合、定義されていません。  
  
-   **_CHAR_UNSIGNED** 既定の場合は、1 として定義されている `char` 型が符号なし。 これは、場合が設定、 [/J (既定の char 型が符号なし)](../build/reference/j-default-char-type-is-unsigned.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_ _Clr_ver** アプリケーションがコンパイルされたときに使用される共通言語ランタイムのバージョンを表す整数リテラルとして定義します。 フォームのエンコード値 `Mmmbbbbb`, ここで、 `M` 、ランタイムのメジャー バージョン `mm` 、ランタイムのマイナー バージョンと `bbbbb` ビルド番号です。 **_ _Clr_ver** が定義されている場合、 [/clr](../build/reference/clr-common-language-runtime-compilation.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
    ```cpp  
    // clr_ver.cpp  
    // compile with: /clr  
    using namespace System;  
    int main() {  
       Console::WriteLine(__CLR_VER);  
    }  
    ```  
  
-   **_CONTROL_FLOW_GUARD** 場合に 1 として定義されている、 [(有効にする制御フロー ガード)/guard:cf](../build/reference/guard-enable-control-flow-guard.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **__COUNTER\_\_** 0 から開始し、ソース ファイルで使用されるたびに 1 ずつ増加またはソース ファイルのヘッダーに追加される整数リテラルに展開します。 **__COUNTER\_\_** プリコンパイル済みヘッダーを使用すると、その状態を記憶します。 このマクロは、常に定義されます。  
  
     この例では `__COUNTER__` を同じ型の 3 つの異なるオブジェクトに一意の識別子を割り当てます。  `exampleClass` コンス トラクターはパラメーターとして整数を受け取ります。  `main`, 、アプリケーションで型の 3 つのオブジェクトを宣言して `exampleClass`, を使用して、 `__COUNTER__` 一意の識別子パラメーターとして。  
  
    ```cpp  
    // macro__COUNTER__.cpp  
    // Demonstration of __COUNTER__, assigns unique identifiers to  
    // different objects of the same type.  
    // Compile by using: cl /EHsc /W4 macro__COUNTER__.cpp  
    #include <stdio.h>  
  
    class exampleClass {  
        int m_nID;  
    public:  
        // initialize object with a read-only unique ID  
        exampleClass(int nID) : m_nID(nID) {}  
        int GetID(void) { return m_nID; }  
    };  
  
    int main()  
    {  
        // __COUNTER__ is initially defined as 0  
        exampleClass e1(__COUNTER__);  
  
        // On the second reference, __COUNTER__ is now defined as 1  
        exampleClass e2(__COUNTER__);  
  
        // __COUNTER__ is now defined as 2  
        exampleClass e3(__COUNTER__);  
  
        printf("e1 ID: %i\n", e1.GetID());  
        printf("e2 ID: %i\n", e2.GetID());  
        printf("e3 ID: %i\n", e3.GetID());  
  
        // Output  
        // ------------------------------  
        // e1 ID: 0  
        // e2 ID: 1  
        // e3 ID: 2  
  
        return 0;  
    }  
    ```  
  
-   **_ _cplusplus_cli** 200406 C++ としてコンパイルするときの整数リテラル値として定義され、 [/clr](../build/reference/clr-common-language-runtime-compilation.md), 、[/clr: 純粋な](../build/reference/clr-common-language-runtime-compilation.md), 、または [/clr:safe](../build/reference/clr-common-language-runtime-compilation.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。 定義した場合、 **_ _cplusplus_cli** が翻訳単位全体で有効になっています。  
  
    ```cpp  
    // cplusplus_cli.cpp  
    // compile by using /clr  
    #include "stdio.h"  
    int main() {  
       #ifdef __cplusplus_cli  
          printf("%d\n", __cplusplus_cli);  
       #else  
          printf("not defined\n");  
       #endif  
    }  
    ```  
  
-   **_ _cplusplus_winrt** 201009 C++ としてコンパイルするときの整数リテラル値として定義され、 [/ZW (Windows ランタイムのコンパイル)](../build/reference/zw-windows-runtime-compilation.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_CPPRTTI** 場合は、1 として定義されている、 [/GR (ランタイム型情報の有効化)](../Topic/-GR%20\(Enable%20Run-Time%20Type%20Information\).md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_CPPUNWIND** 1 つ以上の場合は、1 として定義されている、 [/GX (例外処理を有効にする)](../Topic/-GX%20\(Enable%20Exception%20Handling\).md), 、[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md), 、または [/EH (例外処理モデル)](../build/reference/eh-exception-handling-model.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_DEBUG** 場合に 1 として定義されている、 [/LDd](../build/reference/md-mt-ld-use-run-time-library.md), 、[/MDd](../build/reference/md-mt-ld-use-run-time-library.md), 、または [/MTd](../build/reference/md-mt-ld-use-run-time-library.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_DLL** 場合に 1 として定義されている、 [/MD](../build/reference/md-mt-ld-use-run-time-library.md) または [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (マルチ スレッド DLL) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **__FUNCDNAME\_\_** を含む文字列リテラルとして定義されている、 [装飾名](../Topic/Decorated%20Names.md) 外側の関数です。 マクロは、関数内でのみ定義されます。  **__FUNCDNAME\_\_** を使用する場合、マクロが展開されていない、 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) または [/P](../build/reference/p-preprocess-to-a-file.md) コンパイラ オプション。  
  
     この例では、 `__FUNCDNAME__`, 、`__FUNCSIG__`, 、および `__FUNCTION__` マクロ関数の情報を表示します。  
  
     [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]  
  
-   **__FUNCSIG\_\_** 、外側の関数のシグネチャを格納する文字列リテラルとして定義します。 マクロは、関数内でのみ定義されます。  **__FUNCSIG\_\_** を使用する場合、マクロが展開されていない、 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) または [/P](../build/reference/p-preprocess-to-a-file.md) コンパイラ オプション。 呼び出し規約は、64 ビット ターゲット コンパイルされると、 `__cdecl` 既定です。 使用状況の例は、次を参照してください。、 `__FUNCDNAME__` マクロです。  
  
-   **__FUNCTION\_\_** 、外側の関数の非装飾名を含む文字列リテラルとして定義されます。 マクロは、関数内でのみ定義されます。  **__FUNCTION\_\_** を使用する場合、マクロが展開されていない、 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) または [/P](../build/reference/p-preprocess-to-a-file.md) コンパイラ オプション。 使用状況の例は、次を参照してください。、 `__FUNCDNAME__` マクロです。  
  
-   **_INTEGRAL_MAX_BITS** 64 整数リテラル値として定義された、ベクター以外の整数型の最大サイズ (ビット) にします。 このマクロは、常に定義されます。  
  
    ```cpp  
    // integral_max_bits.cpp  
    #include <stdio.h>  
    int main() {  
       printf("%d\n", _INTEGRAL_MAX_BITS);  
    }  
    ```  
  
-   **__INTELLISENSE\_\_** Visual Studio IDE の IntelliSense コンパイラ時に 1 を渡すように定義されています。 それ以外の場合、定義されていません。 このマクロを使用すると、IntelliSense コンパイラの詳細については、またはビルドと IntelliSense のコンパイラの切り替えを使用していないコードを保護します。 詳細については、次を参照してください。 [IntelliSense パフォーマンスの低下のトラブルシューティングのヒント](https://blogs.msdn.microsoft.com/vcblog/2011/03/29/troubleshooting-tips-for-intellisense-slowness/)します。  
  
-   **_ISO_VOLATILE** 場合は、1 として定義されている、 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_KERNEL_MODE** 場合は、1 として定義されている、 [/kernel (カーネル モード バイナリの作成)](../build/reference/kernel-create-kernel-mode-binary.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_M_AMD64** 値 100 のコンパイルの場合その対象となる x64 プロセッサは、整数リテラルとして定義します。 それ以外の場合、定義されていません。  
  
-   **_M_ARM** ARM プロセッサがターゲットのコンパイル数の整数リテラル値 7 として定義します。 それ以外の場合、定義されていません。  
  
-   **_M_ARM_ARMV7VE** 場合に 1 として定義されている、 [/arch:ARMv7VE](../build/reference/arch-arm.md) ARM プロセッサがターゲット コンパイルに関するコンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_M_ARM_FP** を指定する整数リテラル値として定義されている [/arch](../build/reference/arch-arm.md) コンパイル ターゲットが ARM プロセッサである場合に、コンパイラ オプションが設定されています。 それ以外の場合、定義されていません。  
  
    -   ない場合は 30 ~ 39 の範囲の **/arch** オプションが指定されて、設定された ARM の既定のアーキテクチャを示す (`VFPv3`)。  
  
    -   範囲の場合は 40 ~ 49 **/arch:VFPv4** 設定されました。  
  
    -   参照してください [/arch (ARM)](../build/reference/arch-arm.md) の詳細。  
  
-   **_M_ARM64** が 64 ビット ARM プロセッサをターゲットのコンパイルの場合は 1 として定義します。 それ以外の場合、定義されていません。  
  
-   **_M_CEE** いずれかの場合は 001 として定義された [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_M_CEE_PURE** 001 場合として定義されている、 [/clr: 純粋な](../build/reference/clr-common-language-runtime-compilation.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_M_CEE_SAFE** 001 場合として定義されている、 [/clr:safe](../build/reference/clr-common-language-runtime-compilation.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_M_FP_EXCEPT** 場合は、1 として定義されている、 [/fp: を除く](../build/reference/fp-specify-floating-point-behavior.md) または [/fp: 厳密な](../build/reference/fp-specify-floating-point-behavior.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_M_FP_FAST** 場合は、1 として定義されている、 [/fp:fast](../build/reference/fp-specify-floating-point-behavior.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_M_FP_PRECISE** 場合は、1 として定義されている、 [/fp: 正確な](../build/reference/fp-specify-floating-point-behavior.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_M_FP_STRICT** 場合は、1 として定義されている、 [/fp: 厳密な](../build/reference/fp-specify-floating-point-behavior.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_M_IX86** 値 600 のコンパイルの場合その対象となる x86 プロセッサは、整数リテラルとして定義します。 このマクロは x64 または ARM コンパイル ターゲットに対して定義されていません。  
  
-   **_M_IX86_FP** を示す整数リテラル値として定義されている、 [/arch](../build/reference/arch-arm.md) コンパイラ オプションが設定された、既定値です。 このマクロがコンパイル ターゲットが、x86 の場合に常に定義されているプロセッサ。 それ以外の場合、定義されていません。 定義した場合、値です。  
  
    -   場合は 0、 **/arch:IA32** コンパイラ オプションを設定します。  
  
    -   場合は、1、 **/arch:SSE** コンパイラ オプションを設定します。  
  
    -   場合は 2、 **/arch:sse2 以上**, 、**/arch:AVX** または **/arch:AVX2** コンパイラ オプションを設定します。 この値には既定値がある場合、 **/arch** コンパイラ オプションが指定されなかった。  **/Arch:AVX** が指定されているマクロ **__AVX\_\_** も定義されています。  **/Arch:AVX2** が指定されている両方 **__AVX\_\_** と **__AVX2\_\_** も定義します。  
  
    -   参照してください [/arch (x86)](../build/reference/arch-x86.md) の詳細。  
  
-   **_M_X64** 値 100 のコンパイルの場合その対象となる x64 プロセッサは、整数リテラルとして定義します。 それ以外の場合、定義されていません。  
  
-   **_MANAGED** 場合に 1 として定義されている、 [/clr](../build/reference/clr-common-language-runtime-compilation.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_MSC_BUILD** コンパイラのバージョン番号のリビジョン番号要素を格納する整数リテラルとして定義します。 リビジョン番号は、ピリオド区切りのバージョン番号の 4 番目の要素です。 たとえば、Visual C コンパイラのバージョン番号が 15.00.20706.01 ある、 **_MSC_BUILD** マクロは 1 に評価します。 このマクロは、常に定義されます。  
  
-   **_MSC_EXTENSIONS** 場合は、1 として定義されている、 [/Ze (言語拡張を有効にする)](../build/reference/za-ze-disable-language-extensions.md) コンパイラ オプションを設定すると、既定であります。 それ以外の場合、定義されていません。  
  
-   **_MSC_FULL_VER** メジャーをエンコードする整数リテラルとして定義されている、マイナー、およびコンパイラのバージョン番号の要素の数をビルドします。 メジャー番号はピリオド区切りのバージョン番号の最初の要素、マイナー番号が 2 番目の要素、およびビルド番号が 3 番目の要素。 たとえば、Visual C コンパイラのバージョン番号が 15.00.20706.01 ある、 **_MSC_FULL_VER** マクロは 150020706 に評価します。 入力 **cl/でしょうか。** コマンドラインでコンパイラのバージョン番号を表示します。 このマクロは、常に定義されます。  
  
-   **_MSC_VER** コンパイラのバージョン番号のメジャーおよびマイナー番号要素をエンコードする整数リテラルとして定義します。 メジャー番号はピリオド区切りのバージョン番号の最初の要素と、マイナー番号は 2 番目の要素。 たとえば、Visual C コンパイラのバージョン番号が 17.00.51106.1 である、 **_MSC_VER** マクロは 1700 に評価します。 入力 **cl/でしょうか。** コマンドラインでコンパイラのバージョン番号を表示します。 このマクロは、常に定義されます。  
  
-   **_MSVC_LANG** コンパイラの対象となる C++ 言語の基準を指定する整数リテラルとして定義します。 場合、マクロは整数リテラル値 201402 C++ としてコンパイルされるときに、 [/std:c では 14](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) コンパイラ オプションは設定された場合、または、既定より大きく設定は指定されていない場合、値と、 [/std:c では最新](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) コンパイラ オプションを設定します。 それ以外の場合、マクロは、定義されていません。  **_MSVC_LANG** マクロと [/std (指定の言語標準バージョン)](../Topic/-std%20\(Specify%20Language%20Standard%20Version\).md) コンパイラ オプションで、Visual Studio 2015 の Update 3 以降を使用できます。  
  
-   **_ _Msvc_runtime_checks** する場合は、1 つは 1 として定義されているは [/RTC](../build/reference/rtc-run-time-error-checks.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_MT** 場合に 1 として定義されている [/MD または/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (マルチ スレッド DLL) または [/MT または/MTd](../build/reference/md-mt-ld-use-run-time-library.md) (マルチ スレッド) を指定します。 それ以外の場合、定義されていません。  
  
-   **_NATIVE_WCHAR_T_DEFINED** 場合に 1 として定義されている、 [/Zc:wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_OPENMP** 場合に、Visual C によって実装される OpenMP 仕様の日付を表す整数リテラル 200203 として定義されている、 [/openmp (OpenMP 2.0 サポートの有効化)](../build/reference/openmp-enable-openmp-2-0-support.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
    ```cpp  
    // _OPENMP_dir.cpp  
    // compile with: /openmp   
    #include <stdio.h>   
    int main() {  
       printf("%d\n", _OPENMP);  
    }  
    ```  
  
-   **_PREFAST\_** 場合に 1 として定義されている、 [/analyze](../build/reference/analyze-code-analysis.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **__TIMESTAMP\_\_** 、C ランタイム ライブラリによって返される省略形、定数値の形式では、現在のソース ファイルの最後に変更された日時を表す文字列リテラルとして定義されている [asctime](../c-runtime-library/reference/asctime-wasctime.md) 機能、たとえば、 `Fri 19 Aug 13:32:58 2016`です。 このマクロは、常に定義されます。  
  
-   **_VC_NODEFAULTLIB** 場合に 1 として定義されている、 [/Zl (既定のライブラリ名の省略)](../build/reference/zl-omit-default-library-name.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
-   **_WCHAR_T_DEFINED** 場合に 1 として定義されている既定の [/Zc:wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) コンパイラ オプションを設定します。  **_WCHAR_T_DEFINED** マクロが定義されているが、値が存在しない場合、 **/Zc:wchar_t-** コンパイラ オプションを設定すると `wchar_t` は、プロジェクトに含まれるシステム ヘッダー ファイルで定義されています。 それ以外の場合、定義されていません。  
  
-   **_WIN32** x 64 またはコンパイル ターゲットが 32 ビット ARM、64 ビット ARM、x86 の場合は 1 として定義します。 それ以外の場合、定義されていません。  
  
-   **_WIN64** コンパイル対象が 64 ビット ARM または x64 とする場合は、1 として定義します。 それ以外の場合、定義されていません。  
  
-   **_WINRT_DLL** と C++ としてコンパイルされた場合に 1 として定義されている [/ZW (Windows ランタイムのコンパイル)](../build/reference/zw-windows-runtime-compilation.md) と [/LD または/LDd](../build/reference/md-mt-ld-use-run-time-library.md) コンパイラ オプションを設定します。 それ以外の場合、定義されていません。  
  
 ATL または MFC ライブラリのバージョンを決定するために使用するプリプロセッサ マクロは、コンパイラによってあらかじめ定義されていません。 これらのマクロは、必須のヘッダーが含まれる前にプリプロセッサ ディレクティブで未定義いるため、ライブラリのヘッダーで定義されます。  
  
-   **_ATL_VER** \< atldef.h > で ATL バージョン番号をエンコードする整数リテラルとして定義します。  
  
-   **_MFC_VER** \< afxver_.h > で MFC のバージョン番号をエンコードする整数リテラルとして定義します。  
  
## <a name="see-also"></a>関連項目  
 [マクロ (C/C++)](../Topic/Macros%20\(C-C++\).md)   
 [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)   
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)