---
title: "例外処理 (MFC) | Microsoft Docs"
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
  - "異常なプログラム実行 [C++]"
  - "アーカイブの例外 [C++]"
  - "アサーション [C++], 例外処理を使う場合"
  - "オートメーション [C++], 例外"
  - "C++ 例外処理, 有効化"
  - "C++ 例外処理, MFC アプリケーション"
  - "C++ 例外処理, 型"
  - "クラス ライブラリ [C++], 例外処理のサポート"
  - "DAO [C++], 例外"
  - "データベースの例外 [C++]"
  - "エラー処理 [C++], および例外"
  - "エラー [C++], 検出 (アサーションによって)"
  - "例外処理 [C++], MFC"
  - "例外処理マクロ [C++]"
  - "例外 [C++], MFC マクロと C++ キーワード"
  - "関数呼び出し, 結果"
  - "キーワード [C++], 例外処理"
  - "マクロ [C++], 例外処理"
  - "マクロ [C++], MFC 例外処理マクロ"
  - "メモリ [C++], メモリ不足の例外"
  - "MFC [C++], 例外"
  - "ODBC 例外 [C++]"
  - "OLE 例外 [C++], MFC の例外処理"
  - "メモリ不足の例外 [C++]"
  - "定義済み例外 [C++]"
  - "要求 (サポートされていないサービスの)"
  - "リソース割り当て例外"
  - "リソース [C++], 割り当て"
  - "シリアル化 [C++], 例外"
  - "Windows [C++], リソース割り当て例外"
ms.assetid: 0926627d-2ba7-44a6-babe-d851a4a2517c
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 例外処理 (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、MFC の例外処理機構について説明します。  次の 2 つの機構があります。  
  
-   MFC 3.0 以降で使用できる C\+\+ 例外処理機構  
  
-   MFC 1.0 以降で使用できるマクロ ベースの例外処理機構  
  
 MFC を使用するプログラムを新規作成する場合は、新しい C\+\+ 例外処理機構を使ってください。  既存のプログラムでマクロ ベースの例外処理機構が広範に使われている場合は、引き続きマクロ ベースの例外処理機構を使うことができます。  
  
 既存のプログラムで使っているマクロ ベースの例外処理は、簡単に C\+\+ 例外処理に変換できます。  コードを変換した場合の利点と、変換のガイドラインについては、「[例外処理 : 古いコードの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)」を参照してください。  
  
 また、既存のプログラムでこれらのマクロを使っている部分はそのまま利用し、新規に付け加えた部分で C\+\+ 例外処理を使うこともできます。  この場合のガイドラインについては、「[例外処理 : MFC 3.0 での変更点](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)」を参照してください。  
  
> [!NOTE]
>  プログラムで C\+\+ 例外処理機構を有効にするには、プロジェクトの \[[プロパティ ページ](../ide/property-pages-visual-cpp.md)\] ダイアログ ボックスの \[C\/C\+\+\] フォルダーで、\[コード生成\] ページの \[C\+\+ の例外を有効にする\] チェック ボックスをオンにします。または、\/GX コンパイラ オプションを使います。  既定は \/GX\- \(例外処理を無効にする\) です。  
  
 ここでは、次のトピックについて説明します。  
  
-   [例外処理を使う場合](#_core_when_to_use_exceptions)  
  
-   [MFC の例外処理のサポート](#_core_mfc_exception_support)  
  
-   [例外処理関連項目](#_core_further_reading_about_exceptions)  
  
##  <a name="_core_when_to_use_exceptions"></a> 例外処理を使う場合  
 プログラム実行中の関数の呼び出し結果には、正常実行、エラー実行、異常実行の 3 種類があります。  次に、それぞれの内容を示します。  
  
-   正常実行  
  
     関数は正常に実行され、呼び出し元に戻ります。  関数の実行結果を示す結果コードが呼び出し側に返される場合もあります。  結果コードの値は関数ごとに厳密に定義されており、予測される実行結果に対応付けられています。  結果コードでは、成功または失敗を報告するばかりでなく、通常の予測範囲内で発生した一種の失敗を示すこともできます。  たとえば、ファイルの状態を示す関数で、ファイルが存在しないことを示す結果コードを返すことができます。  結果コードはいずれかの予測結果を示すものなので、"エラー コード" という用語は使用しません。  
  
-   エラー実行  
  
     呼び出し側が関数に誤った引数を引き渡したとき、または関数を不適切なコンテキストで呼び出したときに、この実行結果が生じます。  この場合はエラーになるので、プログラムの開発中にアサーション チェックによって検出する必要があります。アサーションの詳細については、「[アサーション](../Topic/C-C++%20Assertions.md)」を参照してください。  
  
-   異常実行  
  
     メモリ不足や入出力エラーなど、プログラムで制御できない条件が発生し、関数の実行結果に影響が及ぶ場合は、異常実行と判定されます。  この場合は、例外のスローとキャッチによって異常事態に対処する必要があります。  
  
 例外処理は、特に異常実行に向いた処理方式です。  
  
##  <a name="_core_mfc_exception_support"></a> MFC の例外処理のサポート  
 C\+\+ 例外処理機構を直接使用する場合も、MFC 例外処理マクロを使用する場合も、[CException クラス](../mfc/reference/cexception-class.md) クラスまたは `CException` クラスのオブジェクトを使います。これらのオブジェクトは、フレームワークまたはユーザー プログラムによってスローされます。  
  
 MFC には、次の表にあるような定義済みの例外が用意されています。  
  
|例外クラス|説明|  
|-----------|--------|  
|[CMemoryException クラス](../mfc/reference/cmemoryexception-class.md)|メモリ不足例外|  
|[CFileException クラス](../mfc/reference/cfileexception-class.md)|ファイル例外|  
|[CArchiveException クラス](../mfc/reference/carchiveexception-class.md)|アーカイブ\/シリアル化例外|  
|[CNotSupportedException クラス](../mfc/reference/cnotsupportedexception-class.md)|サポートされていないサービスを要求されたときの応答|  
|[CResourceException クラス](../mfc/reference/cresourceexception-class.md)|Windows リソース割り当て例外|  
|[CDaoException クラス](../mfc/reference/cdaoexception-class.md)|データベース例外 \(DAO クラス\)|  
|[CDBException クラス](../mfc/reference/cdbexception-class.md)|データベース例外 \(ODBC クラス\)|  
|[COleException クラス](../mfc/reference/coleexception-class.md)|OLE 例外|  
|[COleDispatchException クラス](../Topic/COleDispatchException%20Class.md)|ディスパッチ \(オートメーション\) 例外|  
|[CUserException クラス](../mfc/reference/cuserexception-class.md)|メッセージ ボックスでユーザーに警告を与えてから汎用 [CException クラス](../mfc/reference/cexception-class.md) をスローする例外|  
  
> [!NOTE]
>  MFC は、C\+\+ 例外処理と MFC 例外マクロをサポートしていますが、  Windows NT の構造化例外ハンドラー \(SEH: Structured Exception Handler\) は直接にはサポートしていません \(「[構造化例外処理](http://msdn.microsoft.com/library/windows/desktop/ms680657)」を参照\)。  
  
##  <a name="_core_further_reading_about_exceptions"></a> 例外処理関連項目  
 以下の項では、MFC ライブラリの例外処理機構について説明しています。  
  
-   [例外処理 : 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)  
  
-   [例外処理 : 例外の内容の調査](../mfc/exceptions-examining-exception-contents.md)  
  
-   [例外処理 : 例外処理でのオブジェクトの解放](../Topic/Exceptions:%20Freeing%20Objects%20in%20Exceptions.md)  
  
-   [例外処理 : 独自関数からの例外のスロー](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)  
  
-   [例外処理 : データベースの例外](../mfc/exceptions-database-exceptions.md)  
  
-   [例外処理 : OLE の例外](../Topic/Exceptions:%20OLE%20Exceptions.md)  
  
 以下の項では、MFC 3.0 とそれ以前のバージョンの違いについて説明しています。新しい C\+\+ 例外を古いコードと共存させる方法についても説明しています。  
  
-   [例外処理 : MFC 3.0 での変更点](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)  
  
-   [例外処理 : 古いコードの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)  
  
-   [例外処理 : MFC マクロと C\+\+ 例外機構の使用](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)  
  
## 参照  
 [C\+\+ 例外処理](../cpp/cpp-exception-handling.md)   
 [How Do I: Create my Own Custom Exception Classes? \(操作方法: 独自のカスタム例外クラスを作成する\)](http://go.microsoft.com/fwlink/?LinkId=128045)