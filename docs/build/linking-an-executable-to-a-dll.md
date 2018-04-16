---
title: DLL と実行可能ファイルをリンク |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- run time [C++], linking
- dynamic load linking [C++]
- linking [C++], DLLs
- DLLs [C++], linking
- implicit linking [C++]
- explicit linking [C++]
- executable files [C++], linking to DLLs
- loading DLLs [C++]
ms.assetid: 7592e276-dd6e-4a74-90c8-e1ee35598ea3
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6bdc8d4b372a589beb51d2f8a9bc05b1aa241c48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="link-an-executable-to-a-dll"></a>DLL と実行形式のリンク  
  
実行可能ファイルを DLL とリンクするには、次の 2 つの方法があります。  
  
-   *暗黙的リンク*でオペレーティング システムは DLL を読み込むに使用する実行可能ファイルが読み込まれるときに、します。 クライアント実行可能ファイルは、場合と同様関数が静的にリンクされているし、実行可能ファイル内に含まれる DLL のエクスポート関数を呼び出します。 暗黙的リンクとも呼ば*静的読み込み*または*負荷時の動的リンク*です。  
  
-   *明示的リンク*、オペレーティング システムが実行時にオンデマンドで DLL を読み込みます。 明示的なリンクすることで、DLL を使用する実行可能ファイルには、明示的に読み込むし、DLL をアンロードして、DLL によってエクスポートされた関数にアクセスする関数呼び出しを行う必要があります。 静的にリンクされたライブラリ内の関数を呼び出しとは異なりクライアント実行可能ファイルは、関数ポインターを通じて DLL でエクスポートされた関数を呼び出す必要があります。 明示的なリンクとも呼ば*動的負荷*または*実行時の動的リンク*です。  
  
実行可能ファイルは、同じ DLL にリンクするいずれかのリンク方法を使用できます。 さらに、これらのメソッドは相互に排他的です。 はありません。1 つの実行可能ファイルは、暗黙的、DLL にリンクし、明示的にアタッチできる別します。  
  
<a name="determining-which-linking-method-to-use"></a>  
  
## <a name="determine-which-linking-method-to-use"></a>リンク方式の使い分け  
  
暗黙的なリンクまたは明示的なリンクを使用するかどうかは、意思決定がアーキテクチャであることをアプリケーションにする必要があります。 各メソッドに長所と短所があります。  
  
### <a name="implicit-linking"></a>暗黙的リンク  
  
暗黙的リンクは、アプリケーションのコードが DLL のエクスポート関数を呼び出すときに発生します。 DLL 関数を呼び出す実行形式のソース コードをコンパイルまたはアセンブルすると、オブジェクト コード内に外部関数への参照が生成されます。 この外部参照を解決するには、アプリケーションをインポート ライブラリ (.lib) ファイルとリンクする必要があります。インポート ライブラリは、DLL の作成元が提供します。  
  
インポート ライブラリには、DLL を読み込んで、DLL 内の関数呼び出しを実装するコードが含まれるだけです。 リンカーは、インポート ライブラリ内に外部関数を見つけると、その関数のコードは DLL 内にあるものと認識します。 リンカーは、単に DLL コードの場所を実行可能ファイルに記入することによって、外部参照を解決します。システムはプロセスの起動時にこの情報を利用します。  
  
動的にリンクされた参照を含むプログラムが起動されると、プログラムの実行可能ファイル内の情報に従って、必要な DLL を探します。 DLL が見つからないと、システムは処理を停止し、ダイアログ ボックスを表示して、エラーを報告します。 見つかった場合は、DLL モジュールがプロセスのアドレス空間に割り当てられます。  
  
など、初期化と終了コード用のエントリ ポイント関数がある Dll の場合`DllMain`、オペレーティング システム、関数を呼び出します。 エントリ ポイント関数に渡されるパラメーターの 1 つは、DLL がプロセスにアタッチされようとしていることを示すコードになります。 エントリ ポイント関数が TRUE を返さない場合、システムは処理を停止し、エラーを報告します。  
  
最後に、システムはプロセスの実行可能コードを変更し、その DLL 関数の開始アドレスをセットします。  
  
プログラム コードの残りの部分と同じように、DLL コードはプロセスの開始時にプロセスのアドレス空間に割り当てられますが、メモリに読み込まれるのはそれが必要とされたときです。 その結果、`PRELOAD`と`LOADONCALL`不要になった以前のバージョンの Windows で読み込みを制御する .def ファイルによって使用されているコード属性が意味を持ちます。  
  
### <a name="explicit-linking"></a>明示的リンク  
  
暗黙的リンクは最も使いやすい方法なので、多くのアプリケーションは、暗黙的リンクを使います。 ただし、明示的なリンクが必要な場合もあります。 ここでは、明示的リンクを使う一般的な理由について説明します。  
  
-   アプリケーションには、実行時まで読み込まれる DLL の名前がわかりません。 たとえば、アプリケーションでは、起動時の構成ファイルから、DLL と、エクスポートされた関数の名前を取得する可能性があります。  
  
-   プロセスの起動時に、DLL が見つからない場合、オペレーティング システムにより暗黙のリンクを使用するプロセスが終了します。 明示的なリンクを使用するプロセスですがこのような状況で終了していませんし、エラーから回復を試みることができます。 たとえば、プロセスがユーザーにエラーを通知して、ユーザーに DLL への別のパスを指定させることができます。  
  
-   それにリンクする Dll の場合も暗黙的なリンクを使用するプロセスは終了、`DllMain`関数が失敗します。 明示的なリンクを使用するプロセスがこのような状況で終了していません。  
  
-   Windows は、アプリケーションの読み込み時にすべての DLL を読み込むため、暗黙的に多くの DLL とリンクするアプリケーションは、起動に時間がかかることがあります。 起動時のパフォーマンスを向上させるのに、アプリケーションはのみに明示的にリンクするその他の Dll が必要になるまでに読み込み、および待機後すぐに必要な Dll を暗黙的にリンクします。  
  
-   明示的なリンクと、インポート ライブラリを使用してアプリケーションをリンクする必要があります。 DLL 内の変更によってエクスポート序数を変更する場合、明示的なリンクを使用するアプリケーションを呼び出す場合に再リンクはありません`GetProcAddress`へ暗黙的なリンクを使用するアプリケーションの再リンクする必要がありますが、関数の名前、および序数値ではなくを使用して、新しいインポート ライブラリ。  
  
明示的リンクの欠点は、次の 2 つです。  
  
-   DLL がある場合、`DllMain`エントリ ポイント関数では、オペレーティング システム関数を呼び出したスレッドのコンテキストで`LoadLibrary`です。 以前の呼び出しのため、プロセスに DLL が既にアタッチされている場合、エントリ ポイント関数は呼び出されません`LoadLibrary`がなかったに対応する呼び出し、`FreeLibrary`関数。 DLL は、使用する場合、明示的なリンクと、問題が発生することができます、`DllMain`スレッドが既に存在するために、プロセスの各スレッドの初期化を実行する関数と`LoadLibrary`(または`AfxLoadLibrary`) が呼び出されたは初期化されていません。  
  
-   DLL が静的範囲のデータとしてを宣言する場合`__declspec(thread)`、明示的にリンクされている場合は保護違反可能性があります。 呼び出しによって、DLL が読み込まれた後`LoadLibrary`コードがこのデータを参照するたびに保護違反が発生します。 静的範囲のデータには、グローバル スタティック アイテムとローカル スタティック アイテムの両方が含まれます。そのため、DLL を作成するときにする必要がありますか、スレッド ローカル ストレージを使用しないでくださいまたは、DLL の動的な読み込みの潜在的な落とし穴について DLL のユーザーに通知します。 詳細については、次を参照してください。[ダイナミック リンク ライブラリ (Windows SDK) でスレッド ローカル ストレージを使用して](http://msdn.microsoft.com/library/windows/desktop/ms686997)です。  
  
<a name="linking-implicitly"></a>  
  
## <a name="how-to-link-implicitly-to-a-dll"></a>DLL を暗黙的にリンクする方法  
  
DLL を使用するには、暗黙的なリンクすることで、クライアント実行可能ファイルは、DLL のプロバイダーからこれらのファイルを取得する必要があります。  
  
-   1 つまたは複数ヘッダー ファイル (.h ファイル) をエクスポートしたデータ、関数、DLL の C++ クラスの宣言を含むです。 クラス、関数、および DLL によってエクスポートされたデータすべて設定されなければなりません`__declspec(dllimport)`ヘッダー ファイルです。 詳細については、次を参照してください。 [dllexport、dllimport](../cpp/dllexport-dllimport.md)です。  
  
-   実行可能ファイルにリンクするインポート ライブラリ。 リンカーは DLL のビルド時に、インポート ライブラリを作成します。 詳細については、次を参照してください。[です。LIB ファイル](../build/reference/dot-lib-files-as-linker-input.md)です。  
  
-   実際の DLL ファイルです。  
  
DLL を使用するには、暗黙的なリンクすることで、実行可能ファイルは、データ、関数、またはエクスポートされたデータ、関数、およびクラスへの呼び出しを含む各ソース ファイル内の DLL によってエクスポートされた C++ クラスを宣言するヘッダー ファイルを含める必要があります。 コーディングの面から、エクスポート関数の呼び出しは、他の関数呼び出しと同じようには。  
  
実行可能ファイルの呼び出しをビルドするには、インポート ライブラリとリンクする必要があります。 システムを構築または外部メイクファイルを使用する場合は、その他のオブジェクト (.obj) ファイルを列記したインポート ライブラリまたはリンクするライブラリのファイル名を指定します。  
  
オペレーティング システムは、呼び出し実行形式の読み込み時に、DLL ファイルを配置できる必要があります。 つまり、アプリケーションが展開または、アプリケーションがインストールされている場合は、DLL の存在を確認する必要があります。   
  
<a name="linking-explicitly"></a>  
  
## <a name="how-to-link-explicitly-to-a-dll"></a>DLL を明示的にリンクする方法  
  
明示的なリンクで DLL を使用するには、アプリケーションは関数呼び出しを実行時に DLL を明示的に読み込むを確認する必要があります。 DLL と明示的にリンクするには、アプリケーションは、以下の手順を実行します。  
  
-   呼び出す[LoadLibrary](loadlibrary-and-afxloadlibrary.md)、 `LoadLibraryEx`、または同様の関数を DLL を読み込んで、モジュール ハンドルを取得します。  
  
-   呼び出す[GetProcAddress](getprocaddress.md)それぞれに関数ポインターを取得するアプリケーションを呼び出す関数をエクスポートします。 アプリケーションが、ポインターを通じて DLL の関数を呼び出すため、コンパイラは生成しません外部参照は、ため、インポート ライブラリとリンクする必要はありません。 ただし、する必要があります、`typedef`または`using`呼び出すエクスポートされた関数の呼び出しシグネチャを定義するステートメント。   
  
-   呼び出す[FreeLibrary](freelibrary-and-afxfreelibrary.md) DLL の終了時にします。  
  
たとえば、この関数のサンプルを呼び出す`LoadLibrary`"MyDLL"という名前の DLL をロードを呼び出す`GetProcAddress`"DLLFunc1"という名前の関数へのポインターを取得する関数を呼び出すと、その結果、保存しを呼び出します`FreeLibrary`DLL をアンロードします。 
  
```C  
#include "windows.h"

typedef HRESULT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT*);  

HRESULT LoadAndCallSomeFunction(DWORD dwParam1, UINT * puParam2)  
{
    HINSTANCE hDLL;               // Handle to DLL  
    LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer  
    HRESULT hrReturnVal;  
      
    hDLL = LoadLibrary("MyDLL");  
    if (NULL != hDLL)  
    {  
        lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL, "DLLFunc1");  
        if (NULL != lpfnDllFunc1)  
        {  
            // call the function  
            hrReturnVal = lpfnDllFunc1(dwParam1, puParam2);  
        }  
        else  
        {  
            // report the error  
            hrReturnVal = ERROR_DELAY_LOAD_FAILED;  
        }
        FreeLibrary(hDLL);
    }
    else
    {
        hrReturnVal = ERROR_DELAY_LOAD_FAILED;
    }  
    return hrReturnVal;
}
```  
  
異なり、この例ではほとんどの場合、呼び出す必要があります`LoadLibrary`と`FreeLibrary`関数を繰り返し指定された dll の場合、DLL の複数の関数を呼び出したり、DLL を呼び出すしようとしている場合は特に、アプリケーションで 1 回だけです。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [インポート ライブラリとエクスポート ファイル](../build/reference/working-with-import-libraries-and-export-files.md)  
  
-   [Windows が使用する dll 検索パス](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## <a name="see-also"></a>参照  
 [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)