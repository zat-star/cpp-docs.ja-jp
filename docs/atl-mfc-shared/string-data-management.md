---
title: "文字列データ管理 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "Unicode, 文字列オブジェクト"
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 文字列データ管理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ は文字列データを管理するいくつかの方法が用意されています:  
  
-   C スタイルの null で終わる文字列を使用する[文字列操作](../c-runtime-library/string-manipulation-crt.md)  
  
-   管理の文字列の Win32 API 関数  
  
-   柔軟性が提供する MFC クラスの [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)、サイズ変更可能な文字列オブジェクト。  
  
-   [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)をクラス、`CString`と同じ機能を MFC 依存しない文字列オブジェクトに提供します。  
  
 ほぼすべてのプログラムは、文字列データを使用します。  MFC の `CString` のクラスは、柔軟な文字列の処理に最も適しています。  7.0 以降、`CString` は、MFC または MFC に依存しないプログラムで使用できます。  ランタイム ライブラリと `CString` は、Unicode または MBCS プログラミングで、がマルチバイト 、ワイド文字を含む文字列をサポートします。  
  
 ここでは、クラス ライブラリの文字列操作に関連する提供する汎用サービスについて説明します。  ここで説明するトピックは次のとおりです。:  
  
-   [Unicode と MBCS は移植性があります。](#_core_unicode_and_mbcs_provide_portability)  
  
-   [CString および定数は、ポインターをを](#_core_cstrings_and_const_char_pointers)  
  
-   [CString の参照カウント](#_core_cstring_reference_counting)  
  
 [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md) のクラスは、文字列の操作をサポートします。  通常、C ランタイム ライブラリの文字列のパッケージで提供される機能を置き換え、拡張することを前提とします。  これらのような処理で基本文字列の `CString` のクラスの提供するメンバー関数と演算子が見つかりました。  クラスは、**CStrings** および標準 C\+\+ 文字列のデータ型を構築し、割り当てること、および比較するコンストラクターと演算子が用意されています。  `CString` が `CObject`から派生していないため、MFC \(Microsoft Foundation Class\) ライブラリ\) のほとんどではなく `CString` オブジェクトを使用できます。  
  
 `CString` オブジェクトは値に基づいて操作が決定されます。`CString` のオブジェクトは一意の値を表します。  文字列に実際の文字列ではなくポインターとして `CString` に注意してください。  
  
 `CString` のオブジェクトは、文字の可変数のシーケンスを表します。  `CString` のオブジェクトは、文字の配列として考えることができます。  
  
##  <a name="_core_unicode_and_mbcs_provide_portability"></a> Unicode と MBCS は移植性があります。  
 MFC Version 3.0 以降では、MFC は、`CString`が Unicode とマルチバイト文字セット \(MBCS\) の両方に対して、が有効になります。  このサポートには、Unicode または ANSI 文字の場合、ビルドできる移植可能なアプリケーションを作成できるようにしやすくします。  この移植性を有効にするには、`CString` オブジェクトの各文字はとしてアプリケーションをビルド、または `char` それ以外の場合はです **\_UNICODE** ときにシンボルが定義されている場合、型 **TCHAR**の `wchar_t` として定義されます。  `wchar_t` の文字は、16 ビットです。  MBCS はシンボル **\_MBCS** ビルド定義すると有効になります。  MFC 自体は **\_MBCS** 記号 \(NAFX ライブラリの場合\) または定義された **\_UNICODE** のシンボル \(UAFX ライブラリ用\) ビルドします。  
  
> [!NOTE]
>  どのフォームまたは移動する文字の文字列のこれ `CString` の例や文字列に含まれる文書が正しく **\_T** マクロを使用して Unicode での移植性には、書式設定された文字の文字列を示します:  
  
 `L"literal string"`  
  
> [!NOTE]
>  コンパイラは Unicode 文字列として扱うかを示します。  たとえば、次のコード:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/CPP/string-data-management_1.cpp)]  
  
> [!NOTE]
>  **\_UNICODE** が ANSI 文字列と、定義されている場合はない Unicode 文字列として変換されます。  詳細については、" " [Unicode とマルチバイト文字セット \(MBCS: Multibyte Character Set\) のサポート](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)を参照してください。  
  
 `CString` のオブジェクトは **INT\_MAX** まで \(2,147,483,647\) の文字を格納できます。  取得するに **TCHAR** のデータ型が使用されます。または設定するに `CString` 内の個々の文字を追加します。  文字配列とは異なり、`CString` のクラスに組み込みメモリ割り当ての機能があります。  これは `CString` のオブジェクトが自動的に必要に応じて拡張できます \(つまり、該当する長い文字列への `CString` のオブジェクトの開発を気にする必要はありません\)。  
  
##  <a name="_core_cstrings_and_const_char_pointers"></a> CString および定数は、ポインターをを  
 `CString` のオブジェクトは、Unicode の下に **const char\*** と同じでない場合は\) 文字の C スタイルの文字列 \( `PCXSTR`のように、機能できます。  [CSimpleStringT::operator PCXSTR](../Topic/CSimpleStringT::operator%20PCXSTR.md) の変換演算子は `CString` のオブジェクトは自由な関数呼び出しの文字のポインターの代わりになるようにします。  **CString\( LPCWSTR**`pszSrc`**\)** のコンストラクターは、文字のポインターが `CString` のオブジェクトに代入されるようにします。  
  
 その `CString` のオブジェクトを圧縮は行われません。  `Chicago`を含む `CString` の 2 種類のオブジェクトを行った場合、たとえば `Chicago` の文字は 2 か所に格納されます。   \(これは、MFC の将来のバージョンの場合は、に依存しないでください。\)  
  
> [!NOTE]
>  直接文字に非定数ポインターとして `CString` にアクセスする必要がある場合 [CSimpleStringT::GetBuffer](../Topic/CSimpleStringT::GetBuffer.md) と [CSimpleStringT::ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md) のメンバー関数を使用します。  
  
> [!NOTE]
>  `BSTR` のオブジェクトを使用して \(以前の OLE オートメーション\) と呼ばれるオートメーションで使用される割り当てと設定に [CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md) と [CStringT::SetSysString](../Topic/CStringT::SetSysString.md) のメンバー関数。  
  
> [!NOTE]
>  可能な場合は、ヒープではなく、フレーム `CString` のオブジェクトを割り当てます。  これは、メモリを節約し、パラメーターの引き渡しを簡単になります。  
  
 `CString` のクラスは、Microsoft Foundation Class ライブラリのコレクション クラスとして `CString` のコレクション内でのオブジェクト要素として確実に格納することもできますが、実行されません。  
  
##  <a name="_core_cstring_reference_counting"></a> CString の参照カウント  
 MFC バージョン 4.0 の時点で、[CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md) のオブジェクトがコピーされると、MFC はインクリメントしてデータをコピーではなく参照の数が表示されます。  これにより、有効な値と値を返す `CString` のオブジェクトをパラメーターを渡すことになります。  これらの操作ではコピー コンストラクターが、場合によっては複数回呼び出します。  参照カウントをインクリメントすることは、これらの一般的な操作のオーバーヘッドを減少し、`CString` 使用して人目を引くを選択します。  
  
 各コピーが破棄されると、元のオブジェクトの参照カウントがデクリメントされます。  元の `CString` のオブジェクトは参照カウントがゼロに低下するまで破棄されません。  
  
 参照カウントを無効または有効にするには `CString` のメンバー関数 [CSimpleStringT::LockBuffer](../Topic/CSimpleStringT::LockBuffer.md) と [CSimpleStringT::UnlockBuffer](../Topic/CSimpleStringT::UnlockBuffer.md) を使用できます。  
  
## 参照  
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)