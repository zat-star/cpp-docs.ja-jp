---
title: "Unicode およびマルチバイト文字セット (MBCS) のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- MFC [C++], character set support
- MBCS [C++], strings and MFC support
- strings [C++], MBCS support in MFC
- character sets [C++], multibyte
- Unicode [C++], MFC strings
- Unicode [C++], string objects
- strings [C++], Unicode
- strings [C++], character set support
ms.assetid: 44b3193b-c92d-40c5-9fa8-5774da303cce
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea35f36012eb893d8784c626c533690e97b517e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unicode とマルチバイト文字セット (MBCS: Multibyte Character Set) のサポート
日本語や中国語などの一部の言語は巨大な文字セットを扱います。 これらの言語に対応するために MFC では巨大な文字セットを処理する 2 つの機能が用意されています。  
  
-   [Unicode](#_core_mfc_support_for_unicode_strings)  
  
-   [マルチバイト文字セット (MBCS)](#_core_mfc_support_for_mbcs_strings)  
  
 すべての新しい開発に Unicode を使用する必要があります。  
  
##  <a name="_core_mfc_support_for_unicode_strings"></a>MFC の Unicode 文字列のサポート  
 MFC 全般で、条件を指定することで Unicode 文字および文字列が利用できます。 具体的には、クラス[CString](../atl-mfc-shared/reference/cstringt-class.md)が Unicode に対応します。  
  
|||||  
|-|-|-|-|  
|UAFXCW.LIB|UAFXCW.PDB|UAFXCWD.LIB|UAFXCWD.PDB|  
|MFC*xx*U.LIB|MFC*xx*U.PDB|MFC*xx*U.DLL|MFC*xx*UD です。LIB|  
|MFC*xx*UD です。PDB ファイル|MFC*xx*UD です。DLL|MFCS*xx*U.LIB|MFCS*xx*U.PDB|  
|MFCS*xx*UD です。LIB|MFCS*xx*UD です。PDB ファイル|MFCM*xx*U.LIB|MFCM*xx*U.PDB|  
|MFCM*xx*U.DLL|MFCM*xx*UD です。LIB|MFCM*xx*UD です。PDB ファイル|MFCM*xx*UD です。DLL|  
  
 (*xx*ファイルのバージョン番号を表すたとえば、'80'、バージョン 8.0)。  
  
 `CString` は `TCHAR` データ型に基づいています。 プログラムをビルドするときに `_UNICODE` シンボルが定義されている場合、`TCHAR` は、16 ビット文字エンコードの `wchar_t` 型として定義されます。 それ以外の場合、`TCHAR` は、通常の 8 ビット文字エンコードである `char` として定義されます。 このため、Unicode を使用するときは、`CString` を 16 ビット幅の文字で構成します。 Unicode を使用しないときは、`char` 型文字で構成します。  
  
 アプリケーションを Unicode 対応にするには、次のことも行う必要があります。  
  
-   条件によってリテラル文字列を Unicode に移植するときは `_T` マクロを使用します。  
  
-   文字列を引数として渡すときは、その関数が文字列の長さを文字数とバイト数のどちらで数えるのかを注意してください。 Unicode 文字列を使用するときは、文字数とバイト数の長さが異なります。  
  
-   C ランタイム ライブラリの文字列操作関数は Unicode 対応バージョンを使用してください。  
  
-   文字および文字へのポインターには、以下の型を使用してください。  
  
    -   `TCHAR`使用する`char`です。  
  
    -   `LPTSTR`使用する`char*`です。  
  
    -   `LPCTSTR`使用する`const char*`です。 `CString` には、`LPCTSTR` と `CString` を相互に変換するための、演算子 `LPCTSTR` が用意されています。  
  
 `CString` のコンストラクター、代入演算子、比較演算子は Unicode を適切に処理します。  
  
 Unicode プログラミングの関連情報については、次を参照してください。 [Unicode トピック](../mfc/unicode-in-mfc.md)です。 [ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)文字列処理関数のすべてのポータブル バージョンを定義します。 カテゴリを参照してください[国際化](../c-runtime-library/internationalization.md)です。  
  
##  <a name="_core_mfc_support_for_mbcs_strings"></a>MFC の MBCS 文字列のサポート  
  
 このクラス ライブラリではマルチバイト文字セットもサポートされていますが、サポートされているのは、2 バイト文字セット (DBCS: Double-Byte Character Sets) のみです。  
  
 マルチバイト文字セットでは、文字は 1 バイト幅または 2 バイト幅になります。 2 バイト幅の文字では 1 バイト目が "先行バイト" になり、特定の範囲の文字を含むコード ページを指定します。 先行バイトと 2 バイト目の "後続バイト" を組み合わせると、そのコードが表す文字が決まります。  
  
 プログラムをビルドするときに `_MBCS` シンボルが定義されていると、`TCHAR` 型 (`CString` はこの型に基づいています) は `char` 型にマップされます。 _MBCS シンボルを定義したときは、`CString` 中のどのバイトが先行バイトであり、どのバイトが後続バイトであるかはプログラマが判定してください。 この判定用の関数は C ランタイム ライブラリで定義されています。  
  
 DBCS では、文字列の中に任意の ANSI の 1 バイト文字と 2 バイト文字を混在させることができます。 したがって、DBCS では文字列の解析時に特別な注意が必要です。 このようなリソースとして、`CString` オブジェクトがあります。  
  
> [!NOTE]
>  MFC における Unicode 文字列のシリアル化は、Unicode 文字列と MBCS 文字列の両方について、どちらのバージョンのアプリケーションを使用しているのかを考慮せずに読み込むことができます。 データ ファイルはプログラムの Unicode 版と MBCS 版の間で移植性があります。  
  
 `CString` のメンバー関数は、特別な "汎用テキスト" バージョンの C ランタイム ライブラリ関数を使用します。つまり、Unicode 対応の関数を使用します。 したがって、たとえば、`CString` のメンバー関数が通常 `strcmp` を呼び出す場所では、代わりに "汎用テキスト" 関数 `_tcscmp` を呼び出します。 シンボル `_MBCS` および `_UNICODE` の定義状況に応じて、`_tcscmp` は次のようにマップされます。  
  
|||  
|-|-|  
|`_MBCS` の定義|`_mbscmp`|  
|`_UNICODE` の定義|`wcscmp`|  
|どちらのシンボルも定義されていない場合|`strcmp`|  
  
> [!NOTE]
>  シンボル `_MBCS` と `_UNICODE` は同時に使用できません。  
  
 汎用テキスト関数マッピングがすべての実行時間の文字列操作ルーチンは、後ほど[C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)です。 具体的を参照してください[国際化](../c-runtime-library/internationalization.md)です。  
  
 同様に、各種の `CString` メソッドについても、"汎用" のデータ型マッピングを使用して実装されます。 MBCS および Unicode への対応を維持するために、MFC では `TCHAR` の代わりに `char`、`LPTSTR` の代わりに `char*`、`LPCTSTR` の代わりに `const char*` を使用しています。 これによって、MBCS または Unicode への正しいマッピングが確保されます。  
  
## <a name="see-also"></a>参照  
 [文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [文字列操作](../c-runtime-library/string-manipulation-crt.md)

