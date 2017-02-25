---
title: "例外処理 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.exceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (データ アクセス オブジェクト), 例外"
  - "例外処理マクロ"
  - "例外, MFC スロー関数"
  - "例外, 処理"
  - "マクロ, 例外処理"
  - "MFC, 例外"
  - "OLE 例外, MFC 関数"
  - "終了関数, MFC"
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# 例外処理
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラムの実行時に、"例外" と呼ばれるさまざまな異常状態やエラーが発生することがあります。  例外には、実行時のメモリ不足、リソースの割り当てエラー、ファイル検索のエラーなどがあります。  
  
 Microsoft Foundation Class ライブラリでは、ANSI C\+\+ 標準で提唱される異常状態の扱いと同じ例外処理機構を使用します。  異常状態に陥る可能性のある関数を呼び出す前に、例外ハンドラーがセットアップされている必要があります。  関数で異常状態が発生した場合は、例外がスローされ、制御が例外ハンドラーに移ります。  
  
 Microsoft Foundation Class ライブラリには、例外ハンドラーをセットアップするいくつかのマクロが用意されています。  ほかにも、必要に応じて特別な例外をスローしプログラムを終了させる補助となる、多くのグローバル関数があります。  これらのマクロやグローバル関数は次のカテゴリに分類されます。  
  
-   例外ハンドラーを組み立てる[例外処理マクロ](#_mfc_exception_macros)  
  
-   特定の型の例外を生成する[例外スロー関数](#_mfc_exception.2d.throwing_functions)  
  
-   プログラムを終了させる[終了関数](#_mfc_termination_functions)  
  
 例外処理の例や詳細については、「[例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md)」を参照してください。  
  
### 例外処理マクロ  
  
|||  
|-|-|  
|[TRY](../Topic/TRY.md)|例外処理をするコード ブロックを指定します。|  
|[CATCH](../Topic/CATCH.md)|**TRY** ブロックでの例外をキャッチするためのコード ブロックを指定します。|  
|[CATCH\_ALL](../Topic/CATCH_ALL.md)|**TRY** ブロックでのすべての例外をキャッチするためのコード ブロックを指定します。|  
|[AND\_CATCH](../Topic/AND_CATCH.md)|**TRY** ブロックでの付加的な例外をキャッチするためのコード ブロックを指定します。|  
|[AND\_CATCH\_ALL](../Topic/AND_CATCH_ALL.md)|**TRY** ブロックでのすべての付加的な例外をキャッチするためのコード ブロックを指定します。|  
|[END\_CATCH](../Topic/END_CATCH.md)|直前の **CATCH** または `AND_CATCH` ブロックの終わりを示します。|  
|[END\_CATCH\_ALL](../Topic/END_CATCH_ALL.md)|直前の `CATCH_ALL` ブロックの終わりを示します。|  
|[THROW](../Topic/THROW%20\(MFC\).md)|指定された例外をスローします。|  
|[THROW\_LAST](../Topic/THROW_LAST.md)|現在処理されている例外を 1 つ外側のハンドラーにスローします。|  
  
### 例外スロー関数  
  
|||  
|-|-|  
|[AfxThrowArchiveException](../Topic/AfxThrowArchiveException.md)|アーカイブの例外をスローします。|  
|[AfxThrowFileException](../Topic/AfxThrowFileException.md)|ファイルの例外をスローします。|  
|[AfxThrowMemoryException](../Topic/AfxThrowMemoryException.md)|メモリの例外をスローします。|  
|[AfxThrowNotSupportedException](../Topic/AfxThrowNotSupportedException.md)|サポートしていない機能にアクセスしたときの例外をスローします。|  
|[AfxThrowResourceException](../Topic/AfxThrowResourceException.md)|Windows のリソースが見つからないときの例外をスローします。|  
|[AfxThrowUserException](../Topic/AfxThrowUserException.md)|ユーザーが起動したプログラムの動作での例外をスローします。|  
  
 MFC ライブラリには、OLE 例外専用の 2 つの例外スロー関数が用意されています。  
  
### OLE 例外関数  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md)|OLE オートメーション関数内の例外をスローします。|  
|[AfxThrowOleException](../Topic/AfxThrowOleException.md)|OLE の例外をスローします。|  
  
 データベースの例外をサポートするため、データベース クラスには 2 つの例外処理クラス `CDBException` と `CDaoException`、およびこの例外クラス型をサポートするグローバル関数が用意されています。  
  
### DAO 例外関数  
  
|||  
|-|-|  
|[AfxThrowDAOException](../Topic/AfxThrowDaoException.md)|独自に作成したコードから [CDaoException](../../mfc/reference/cdaoexception-class.md) をスローします。|  
|[AfxThrowDBException](../Topic/AfxThrowDBException.md)|独自に作成したコードから [CDBException](../../mfc/reference/cdbexception-class.md) をスローします。|  
  
 MFC に用意されている終了関数を次に示します。  
  
### 終了関数  
  
|||  
|-|-|  
|[AfxAbort](../Topic/AfxAbort.md)|致命的なエラーが発生したときに、アプリケーションの実行を終了するために呼び出されます。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)