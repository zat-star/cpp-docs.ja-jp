---
title: "Unicode とマルチバイト文字セット (MBCS: Multibyte Character Set) のサポート | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC [C++]、文字セットのサポート"
  - "MBCS [C++]、文字列、および MFC サポート"
  - "文字列 [C++]、MFC の MBCS のサポート"
  - "文字セット [C++]、マルチバイト"
  - "Unicode [C++]、MFC 文字列"
  - "Unicode [C++]、文字列オブジェクト"
  - "文字列 [C++]、Unicode"
  - "文字列 [C++]、文字セットのサポート"
ms.assetid: 44b3193b-c92d-40c5-9fa8-5774da303cce
caps.latest.revision: 17
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Unicode とマルチバイト文字セット (MBCS: Multibyte Character Set) のサポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

日本語や中国語などの一部の言語は巨大な文字セットを扱います。  これらの言語に対応するために MFC では巨大な文字セットを処理する 2 つの機能が用意されています。  
  
-   [Unicode](#_core_mfc_support_for_unicode_strings)  
  
-   [マルチバイト文字セット \(MBCS\)](#_core_mfc_support_for_mbcs_strings)  
  
 すべての新しい開発に Unicode を使用する必要があります。  
  
##  <a name="_core_mfc_support_for_unicode_strings"></a> MFC がサポートする Unicode 文字列  
 MFC 全般で、条件を指定することで Unicode 文字および文字列が利用できます。  [CString](../atl-mfc-shared/reference/cstringt-class.md) クラスでは Unicode がサポートされています。  
  
|||||  
|-|-|-|-|  
|UAFXCW.LIB|UAFXCW.PDB|UAFXCWD.LIB|UAFXCWD.PDB|  
|MFC*xx*U.LIB|MFC*xx*U.PDB|MFC*xx*U.DLL|MFC*xx*UD.LIB|  
|MFC*xx*UD.PDB|MFC*xx*UD.DLL|MFCS*xx*U.LIB|MFCS*xx*U.PDB|  
|MFCS*xx*UD.LIB|MFCS*xx*UD.PDB|MFCM*xx*U.LIB|MFCM*xx*U.PDB|  
|MFCM*xx*U.DLL|MFCM*xx*UD.LIB|MFCM*xx*UD.PDB|MFCM*xx*UD.DLL|  
  
 \(*xx* はファイルのバージョン番号を表します。たとえば、80 は Version 8.0 を表します。\)  
  
 `CString` は `TCHAR` データ型に基づいています。  プログラムをビルドするときに `_UNICODE` シンボルが定義されている場合、`TCHAR` は、16 ビット文字エンコードの `wchar_t` 型として定義されます。  それ以外の場合、`TCHAR` は、通常の 8 ビット文字エンコードである `char` として定義されます。  このため、Unicode を使用するときは、`CString` を 16 ビット幅の文字で構成します。  Unicode を使用しないときは、`char` 型文字で構成します。  
  
 アプリケーションを Unicode 対応にするには、次のことも行う必要があります。  
  
-   条件によってリテラル文字列を Unicode に移植するときは `_T` マクロを使用します。  
  
-   文字列を引数として渡すときは、その関数が文字列の長さを文字数とバイト数のどちらで数えるのかを注意してください。  Unicode 文字列を使用するときは、文字数とバイト数の長さが異なります。  
  
-   C ランタイム ライブラリの文字列操作関数は Unicode 対応バージョンを使用してください。  
  
-   文字および文字へのポインターには、以下の型を使用してください。  
  
    -   `TCHAR` 通常は `char` 型にするデータ。  
  
    -   `LPTSTR` 通常は `char*` 型にするデータ。  
  
    -   `LPCTSTR` 通常は `const char*` 型にするデータ。  `CString` には、`CString` と `LPCTSTR` を相互に変換するための、演算子 `LPCTSTR` が用意されています。  
  
 `CString` のコンストラクター、代入演算子、比較演算子は Unicode を適切に処理します。  
  
 Unicode プログラミングの関連情報については、「[Unicode](../mfc/unicode-in-mfc.md)」を参照してください。  「[ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)」では、文字列処理関数のすべてについて移植性が高いバージョンを定義しています。  「[国際化](../c-runtime-library/internationalization.md)」を参照してください。  
  
##  <a name="_core_mfc_support_for_mbcs_strings"></a> MFC がサポートする MBCS 文字列  
  
> [!WARNING]
>  MBCS 文字列はレガシ テクノロジです。新しいプロジェクトにはお勧めしません。  次の情報は、MBCS を使用する既存のコードの維持に必要なシナリオを対象としています。Unicode を使用するためのコードのアップグレードには適していません。  
  
 このクラス ライブラリではマルチバイト文字セットもサポートされていますが、サポートされているのは、2 バイト文字セット \(DBCS: Double\-Byte Character Sets\) のみです。  
  
> [!IMPORTANT]
>  [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] 以降では、MFC DLL の MBCS バージョンは、MSDN のダウンロード サイトから Visual Studio の無料のアドインとして入手できます。  詳細については、[MFC MBCS DLL アドイン](../mfc/mfc-mbcs-dll-add-on.md)を参照してください。  
  
 マルチバイト文字セットでは、文字は 1 バイト幅または 2 バイト幅になります。  2 バイト幅の文字では 1 バイト目が "先行バイト" になり、特定の範囲の文字を含むコード ページを指定します。  先行バイトと 2 バイト目の "後続バイト" を組み合わせると、そのコードが表す文字が決まります。  
  
 プログラムをビルドするときに `_MBCS` シンボルが定義されていると、`TCHAR` 型 \(`CString` はこの型に基づいています\) は `char` 型にマップされます。  \_MBCS シンボルを定義したときは、`CString` 中のどのバイトが先行バイトであり、どのバイトが後続バイトであるかはプログラマが判定してください。  この判定用の関数は C ランタイム ライブラリで定義されています。  
  
 DBCS では、文字列の中に任意の ANSI の 1 バイト文字と 2 バイト文字を混在させることができます。  したがって、DBCS では文字列の解析時に特別な注意が必要です。  このようなリソースとして、`CString` オブジェクトがあります。  
  
> [!NOTE]
>  MFC における Unicode 文字列のシリアル化は、Unicode 文字列と MBCS 文字列の両方について、どちらのバージョンのアプリケーションを使用しているのかを考慮せずに読み込むことができます。  データ ファイルはプログラムの Unicode 版と MBCS 版の間で移植性があります。  
  
 `CString` のメンバー関数は、特別な "汎用テキスト" バージョンの C ランタイム ライブラリ関数を使用します。つまり、Unicode 対応の関数を使用します。  したがって、たとえば、`CString` のメンバー関数が通常 `strcmp` を呼び出す場所では、代わりに "汎用テキスト" 関数 `_tcscmp` を呼び出します。  シンボル `_MBCS` および `_UNICODE` の定義状況に応じて、`_tcscmp` は次のようにマップされます。  
  
|||  
|-|-|  
|`_MBCS` の定義|`_mbscmp`|  
|`_UNICODE` の定義|`wcscmp`|  
|どちらのシンボルも定義されていない場合|`strcmp`|  
  
> [!NOTE]
>  シンボル `_MBCS` と `_UNICODE` は同時に使用できません。  
  
 すべてのランタイム文字列処理ルーチンに対する汎用テキスト関数マッピングについては、「[C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)」を参照してください。  特に、「[国際化](../c-runtime-library/internationalization.md)」を参照してください。  
  
 同様に、各種の `CString` メソッドについても、"汎用" のデータ型マッピングを使用して実装されます。  MBCS および Unicode への対応を維持するために、MFC では `char` の代わりに `TCHAR`、`char*` の代わりに `LPTSTR`、`const char*` の代わりに `LPCTSTR` を使用しています。  これによって、MBCS または Unicode への正しいマッピングが確保されます。  
  
## 参照  
 [文字列](../atl-mfc-shared/strings-atl-mfc.md)   
 [文字列操作](../c-runtime-library/string-manipulation-crt.md)