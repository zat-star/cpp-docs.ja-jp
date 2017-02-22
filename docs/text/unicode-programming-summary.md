---
title: "Unicode プログラミングの要約 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unicode [C++], MFC および C のランタイム関数"
  - "Unicode [C++], プログラミング"
ms.assetid: a4c9770f-6c9c-447c-996b-980920288bed
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Unicode プログラミングの要約
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unicode に対する MFC や C のランタイム機能のサポートを有効にするには、次のようにします。  
  
-   **\_UNICODE** を定義する。  
  
     シンボル **\_UNICODE** を定義してプログラムをビルドします。  
  
-   エントリ ポイントを指定する。  
  
     プロジェクトの \[[プロパティ ページ](../ide/property-pages-visual-cpp.md)\] ダイアログ ボックスで、\[リンカー\] フォルダーの \[出力\] ページにある \[エントリ ポイント\] を **wWinMainCRTStartup** に設定します。  
  
-   移植性の高いランタイム関数と型を使用する。  
  
     Unicode 文字列を取り扱う際は、必ず適切な C ランタイム関数を使います。  **wcs** 系関数も使用できますが、完全に移植性の高い \(国際対応の\) **\_TCHAR** マクロを使用することをお勧めします。  これらのマクロにはすべて接頭字 **\_tcs** が付けられ、**str** ファミリの関数と一対一で対応します。  これらの関数については、「ランタイム ライブラリ リファレンス」の「[国際化](../c-runtime-library/internationalization.md)」で詳しく説明されています。  詳細については、「[Tchar.h における汎用テキストのマッピング](../Topic/Generic-Text%20Mappings%20in%20Tchar.h.md)」を参照してください。  
  
     **\_TCHAR** および、この章の「[Unicode のサポート](../text/support-for-unicode.md)」で説明している移植性のあるデータ型を使います。  
  
-   リテラル文字列を正しく処理する。  
  
     Visual C\+\+ コンパイラでは、次のリテラル文字列を  
  
    ```  
    L"this is a literal string"  
    ```  
  
     Unicode 文字の文字列として解釈します。  リテラル文字にも、同じプリフィックスを使うことができます。  **\_T** マクロを使ってリテラル文字列を包括的にコーディングすると、Unicode 環境下の Unicode 文字列として、または Unicode を含めない ANSI 文字列 \(MBCS を含む\) としてコンパイルされます。  たとえば、  
  
    ```  
    pWnd->SetWindowText( "Hello" );  
    ```  
  
     を使う代わりに、  
  
    ```  
    pWnd->SetWindowText( _T("Hello") );  
    ```  
  
     を使うようにします。**\_UNICODE** が定義されていると、**\_T** はリテラル文字列を L プレフィックスが付いた形式に変換します。そうでない場合には、**\_T** は L プレフィックスを付けずに文字列を変換します。  
  
    > [!TIP]
    >  **\_T** マクロは、`_TEXT` マクロと同じです。  
  
-   注意して文字列の長さを関数に渡す。  
  
     文字列の文字数を要求する関数もありますが、バイト数を要求する関数もあります。  たとえば、**\_UNICODE** が定義されていると、`CArchive` オブジェクトへの次の呼び出しは正常に機能しません \(`str` は `CString` 型です\)。  
  
    ```  
    archive.Write( str, str.GetLength( ) );    // invalid  
    ```  
  
     Unicode アプリケーションの場合、文字列の長さは文字数を表しますが、各文字が 2 バイト幅なので、正確なバイト数ではありません。  バイト数を渡す場合は、次のコードを記述する必要があります。  
  
    ```  
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid  
    ```  
  
     このコードにより、正確なバイト数を書き込むことができます。  
  
     これに対して、バイト指向ではなく文字指向の MFC メンバー関数の場合は、この補足コードがなくても正常に機能します。  
  
    ```  
    pDC->TextOut( str, str.GetLength( ) );  
    ```  
  
     `CDC::TextOut` は、バイト数ではなく文字数を取ります。  
  
-   [fopen\_s、\_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) を使用して、Unicode ファイルを開きます。  
  
 Windows 2000 環境の MFC とランタイム ライブラリによる Unicode プログラミングのサポートをまとめると、次のようになります。  
  
-   データベース クラスのメンバー関数を除いて、`CString` を含むすべての MFC 関数は、Unicode に対応しています。  また、`CString` には、Unicode\/ANSI 変換関数も用意されています。  
  
-   ランタイム ライブラリには、すべての文字列操作関数の Unicode バージョンが用意されています。\(また、Unicode や MBCS に適した移植性の高いバージョンとして、  **\_tcs** マクロも用意されています\)。  
  
-   Tchar.h には、リテラル文字列と文字を変換するための移植性のあるデータ型と **\_T** マクロが用意されています。  詳細については、「[Tchar.h における汎用テキストのマッピング](../Topic/Generic-Text%20Mappings%20in%20Tchar.h.md)」を参照してください。  
  
-   ランタイム ライブラリには、**main** のワイド文字バージョンが用意されています。  **wmain** を使用して、アプリケーションが Unicode を認識できるようにします。  
  
## 参照  
 [Unicode のサポート](../text/support-for-unicode.md)