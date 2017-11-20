---
title: "CRT ライブラリの機能 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.runtime
dev_langs: C++
helpviewer_keywords:
- MSVCR71.dll
- libraries [C++], multithreaded
- library files, run-time
- LIBCMT.lib
- LIBCP.lib
- LIBCPMT.lib
- run-time libraries, C
- CRT, release versions
- MSVCP71.dll
- LIBC.lib
- libraries [C++]
- libraries [C++], run-time
- linking [C++], libraries
ms.assetid: a889fd39-807d-48f2-807f-81492612463f
caps.latest.revision: "32"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ed41372637e9ee68db087fbe0ad532d9e6bb4935
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="crt-library-features"></a>CRT ライブラリの機能
ここでは、C ランタイム ライブラリを構成するさまざまな .lib ファイル、および関連するコンパイラ オプションとプリプロセッサ ディレクティブについて説明します。  
  
## <a name="c-run-time-libraries-crt"></a>C ランタイム ライブラリ (CRT)  
 C ランタイム ライブラリ (CRT) は、ISO C99 標準ライブラリが組み込まれている C++ 標準ライブラリの一部です。 この CRT を実装する Visual C++ ライブラリは、ネイティブ コード開発と、ネイティブとマネージの混合コードと .NET 向けの純粋マネージ コードの両方の開発をサポートします。 CRT のすべてのバージョンがマルチスレッド開発をサポートします。 ほとんどのライブラリが、ライブラリを直接コードにリンクする静的リンクと、コードで共通 DLL ファイルを使用できるようにする動的リンクの両方をサポートします。  
  
 Visual Studio 2015 より、CRT が新しいバイナリにリファクタリングされました。 ユニバーサル CRT (UCRT) には、標準の C99 CRT ライブラリからエクスポートされた関数とグローバルが含まれています。 UCRT は Windows コンポーネントであり、Windows 10 の一部として出荷されます。 UCRT 用のスタティック ライブラリ、DLL インポート ライブラリ、およびヘッダー ファイルが Windows 10 SDK に含まれています。 Visual C++ をインストールすると、Visual Studio セットアップによって、UCRT を使用するために必要な Windows 10 SDK のサブセットがインストールされます。 UCRT は、Visual Studio 2015 以降のバージョンでサポートされている Windows の任意のバージョンで使用できます。 Windows 10 以外のサポートされているバージョンの Windows では、vcredist を使用して再配布することができます。 詳細については、「 [Redistributing Visual C++ Files](../ide/redistributing-visual-cpp-files.md)」を参照してください。  
  
 次の表に、UCRT を実装するライブラリの一覧を示します。  
  
|ライブラリ|関連付けられている DLL|特性|オプション|プリプロセッサ ディレクティブ|  
|-------------|--------------------|---------------------|------------|-----------------------------|  
|libucrt.lib|なし|UCRT をコードに静的にリンクします。|**/MT**|_MT|  
|libucrtd.lib|なし|静的リンク用の UCRT のデバッグ バージョン。 再頒布可能パッケージではありません。|**/MTd**|_DEBUG、_MT|  
|ucrt.lib|ucrtbase.dll|UCRT 用の DLL インポート ライブラリ。|**/MD**|_MT、_DLL|  
|ucrtd.lib|ucrtbased.dll|UCRT のデバッグ バージョン用の DLL インポート ライブラリ。 再頒布可能パッケージではありません。|**/MDd**|_DEBUG、_MT、_DLL|  
  
 vcruntime ライブラリには、例外処理やデバッグ サポートなどの Visual C++ CRT 実装固有のコード、ランタイム チェックと型情報、実装の詳細、および特定の拡張ライブラリ関数が含まれています。 このライブラリは、使用されているコンパイラのバージョンによって異なります。  
  
 次の表に、vcruntime ライブラリを実装するライブラリの一覧を示します。  
  
|ライブラリ|関連付けられている DLL|特性|オプション|プリプロセッサ ディレクティブ|  
|-------------|--------------------|---------------------|------------|-----------------------------|  
|libvcruntime.lib|なし|コードに静的にリンクされています。|**/MT**|_MT|  
|libvcruntimed.lib|なし|静的リンク用のデバッグ バージョン。 再頒布可能パッケージではありません。|**/MTd**|_MT、_DEBUG|  
|vcruntime.lib|vcruntime\<version>.dll|vcruntime 用の DLL インポート ライブラリ。|**/MD**|_MT、_DLL|  
|vcruntimed.lib|vcruntime\<version>d.dll|デバッグ vcruntime 用の DLL インポート ライブラリ。 再頒布可能パッケージではありません。|**/MDd**|_DEBUG、_MT、_DLL|  
  
 CRT を初期化するコードは、CRT ライブラリが静的にリンクされているのか、動的にリンクされているのか、ネイティブ コードなのか、マネージ コードなのか、混合コードなのかによって、複数あるライブラリのいずれかに含まれています。 このコードは、CRT のスタートアップ、内部スレッド単位データ初期化、および強制終了を処理します。 使用されているコンパイラのバージョンによって異なります。 このライブラリは、動的にリンクされた UCRT が使用されている場合でも、常に静的にリンクされます。  
  
 次の表に、CRT の初期化と強制終了を実装するライブラリの一覧を示します。  
  
|ライブラリ|特性|オプション|プリプロセッサ ディレクティブ|  
|-------------|---------------------|------------|-----------------------------|  
|LIBCMT.lib|ネイティブ CRT スタートアップをコードに静的にリンクします。|**/MT**|_MT|  
|libcmtd.lib|ネイティブ CRT スタートアップのデバッグ バージョンを静的にリンクします。 再頒布可能パッケージではありません。|**/MTd**|_DEBUG、_MT|  
|msvcrt.lib|DLL UCRT および vcruntime で使用するためのネイティブ CRT スタートアップ用のスタティック ライブラリ。|**/MD**|_MT、_DLL|  
|msvcrtd.lib|DLL UCRT および vcruntime で使用するためのネイティブ CRT スタートアップのデバッグ バージョン用のスタティック ライブラリ。 再頒布可能パッケージではありません。|**/MDd**|_DEBUG、_MT、_DLL|  
|msvcmrt.lib|DLL UCRT および vcruntime で使用するためのネイティブとマネージの混合 CRT スタートアップ用のスタティック ライブラリ。|**/clr**||  
|msvcmrtd.lib|DLL UCRT および vcruntime で使用するためのネイティブとマネージの混合 CRT スタートアップのデバッグ バージョン用のスタティック ライブラリ。 再頒布可能パッケージではありません。|**/clr**||  
|msvcurt.lib|**廃止** 純粋マネージ CRT 用のスタティック ライブラリ。|**/clr:pure**||  
|msvcurtd.lib|**廃止** 純粋マネージ CRT のデバッグ バージョン用のスタティック ライブラリ。 再頒布可能パッケージではありません。|**/clr:pure**||  
  
 C ランタイム ライブラリを指定するコンパイラ オプションを使用せずにコマンド ラインからプログラムをリンクした場合、リンカーは静的にリンクされた CRT ライブラリ (libcmt.lib、libvcruntime.lib、libucrt.lib) を使用します。  
  
 静的にリンクされた CRT を使用すると、暗黙的に、C ランタイム ライブラリによって保存されるステータス情報は CRT のそのインスタンスに対してローカルなものになります。 たとえば、静的にリンクされた CRT を使用している状態で [strtok、_strtok_l、wcstok、_wcstok_l、_mbstok、_mbstok_l](../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) を使用した場合、`strtok` パーサーの位置は、静的な CRT の別のインスタンスにリンクされた同じプロセス内 (ただし DLL または EXE は別) のコードで使用される `strtok` の状態とは無関係になります。 反対に、動的にリンクされた CRT では、CRT に動的にリンクされるプロセス内のすべてのコードに対して状態が共有されます。 この問題は、セキュリティが強化された新しいバージョンの関数では発生しません。たとえば、 `strtok_s` にはこの問題はありません。  
  
 静的な CRT とのリンクによってビルドされた DLL は独自の CRT 状態を持つので、この結果を明確に理解し、期待する場合を除き、DLL 内で CRT に静的にリンクすることは推奨されません。 たとえば、独自の静的な CRT にリンクする DLL を読み込む実行可能ファイルで [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) を呼び出すと、このトランスレータは DLL 内のコードで生成されたハードウェア例外をキャッチしませんが、メインの実行可能ファイル内のコードによって生成されたハードウェア例外をキャッチします。  
  
 **/clr** コンパイラ スイッチを使用すると、コードはスタティック ライブラリ msvcmrt.lib とリンクされます。 このスタティック ライブラリは、マネージ コードとネイティブ CRT 間のプロキシを提供します。 **/MT** は、静的にリンクされる CRT ( **/MTd** オプションまたは **/clr**オプション) と一緒には使用できません。 代わりに、動的にリンクされるライブラリ (**/MD** または **/MDd**) を使用してください。  
  
 **/clr:pure** コンパイラ スイッチを使用すると、コードはスタティック ライブラリ msvcurt.lib とリンクされます。 **/clr**と同様、静的にリンクされるライブラリにはリンクできません。 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 以降では使用されていません。  
  
 **/clr** と共に CTR を使用する方法の詳細については、「[混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)」を参照してください。**/clr:pure** については、「[純粋で検証可能なコード (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。  
  
 アプリケーションのデバッグ バージョンをビルドするには、[_DEBUG](../c-runtime-library/debug.md) フラグが定義され、アプリケーションが上の表のいずれかのライブラリのデバッグ バージョンとリンクされている必要があります。 ライブラリ ファイルのデバッグ バージョンの使い方の詳細については、「 [CRT のデバッグ技術](/visualstudio/debugger/crt-debugging-techniques)」を参照してください。  
  
 この CRT のバージョンは、C99 標準に完全には準拠していません。 具体的には、\<tgmath.h> ヘッダーと CX_LIMITED_RANGE/FP_CONTRACT プラグマ マクロがサポートされていません。 標準 IO 関数内のパラメーター指定子の意味などの特定の要素で、既定で、従来の解釈が使用されます。 /Zc コンパイラ準拠オプションを使用して、リンカー オプションを指定し、ライブラリ準拠の一部の側面を制御することができます。  
  
## <a name="c-standard-library"></a>C++ 標準ライブラリ  
  
|C++ 標準ライブラリ|特性|オプション|プリプロセッサ ディレクティブ|  
|----------------------------|---------------------|------------|-----------------------------|  
|LIBCPMT.lib|マルチスレッド、静的リンク|**/MT**|_MT|  
|MSVCPRT.LIB|マルチスレッド、動的リンク (MSVCP\<version>.dll 用のインポート ライブラリ)|**/MD**|_MT、_DLL|  
|LIBCPMTD.LIB|マルチスレッド、静的リンク|**/MTd**|_DEBUG、_MT|  
|MSVCPRTD.LIB|マルチスレッド、動的リンク (MSVCP\<version>D.DLL 用のインポート ライブラリ)|**/MDd**|_DEBUG、_MT、_DLL|  
  
 プロジェクトのリリース バージョンをビルドすると、既定では、選択したコンパイラ オプション (マルチスレッド、DLL、/clr) に応じて、基本 C ランタイム ライブラリ (LIBCMT.LIB、MSVCMRT.LIB、MSVCRT.LIB) の 1 つがリンクされます。 コードに [C++ 標準ライブラリのヘッダー ファイル](../standard-library/cpp-standard-library-header-files.md)の 1 つがインクルードされている場合は、コンパイル時に Visual C++ によって自動的に C++ 標準ライブラリがリンクされます。 例:  
  
```  
#include <ios>   
```  
  
## <a name="what-problems-exist-if-an-application-uses-more-than-one-crt-version"></a>アプリケーションで複数の CRT バージョンを使用した場合に発生する問題  
 複数の DLL または EXE がある場合は、異なるバージョンの Visual C++ を使用しているかどうかにかかわらず、複数の CRT が使用される可能性があります。 たとえば、CRT を複数の DLL に静的にリンクした場合に同じ問題が発生します。 この静的 CRT の問題が発生した場合は、 **/MD** でコンパイルして CRT DLL を使用するという対処が一般的です。 DLL で DLL 境界を越えて CRT リソースを渡すと、CRT の不一致によって問題が発生します。その場合は、Visual C++ でプロジェクトをコンパイルし直す必要があります。  
  
 複数のバージョンの CRT を使用するプロジェクトでは、DLL の境界を超えて特定の CRT オブジェクト (ファイル ハンドル、ロケール、環境変数など) を渡す場合には注意を要します。 発生する可能性のある問題とその対処法の詳細については、「[DLL の境界を越えて CRT オブジェクトを渡す場合に発生する可能性のあるエラー](../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)