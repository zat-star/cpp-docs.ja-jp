---
title: "例外処理 : データベースの例外 | Microsoft Docs"
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
  - "DAO [C++], 例外"
  - "データベースの例外 [C++]"
  - "データベース [C++], 例外処理"
  - "エラー コード [C++], データベース例外処理"
  - "例外処理 [C++], データベース"
  - "例外 [C++], データベース"
  - "ODBC [C++], 例外"
  - "ODBC 例外 [C++]"
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 例外処理 : データベースの例外
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、データベースの例外を処理する方法について説明します。  この記事の素材のほとんどは、ODBC \(Open Database Connectivity\) の MFC クラスまたはデータ アクセス オブジェクト \(DAO\) の MFC クラスを使用しているかに適用されます。  1 個のまたは他のモデルの素材の仕様は、明示的にマークされます。  ここでは、次の内容について説明します。  
  
-   [例外処理の方法](#_core_approaches_to_exception_handling)  
  
-   [データベースの例外処理の例](#_core_a_database_exception.2d.handling_example)  
  
##  <a name="_core_approaches_to_exception_handling"></a> Exception Handling への方法  
 方法は DAO または ODBC を使用している場合でも同じです。  
  
 ハンドルの例外条件に例外ハンドラーを作成する必要があります。  
  
 データベースの例外のキャッチに最も実際的な方法は、例外のシナリオを使用してアプリケーションをテストします。  コードの操作が原因で発生する可能性のある確認発生する例外が発生する可能性のある例外を示します。  次に、例外がスローされる参照するために、デバッガーで返されるエラー情報を確認する方法を調べるトレース出力を示します。  これにより、リターン コードを使用するシナリオの例外については参照するかを通知します。  
  
### ODBC の例外に使用するエラー コード  
 フレームワークによって定義されたフォーム **AFX\_SQL\_ERROR\_XXX**の名前を持つリターン コードに加えて、[CDBExceptions](../mfc/reference/cdbexception-class.md) は [ODBC\(D\)](../data/odbc/odbc-basics.md) のリターン コードに基づいています。  このような例外のリターン コードにフォーム **SQL\_ERROR\_XXX**の名前があります。  
  
 リターン コードはクラス `CDBException`の [m\_nRetCode](../Topic/CDBException::m_nRetCode.md) のデータ メンバーで—フレームワークで定義され、ODBC 定義された—データベース クラスを返すことができる説明しています。  ODBC によって定義されるリターン コードに関する追加情報については、MSDN ライブラリの" ODBC SDK *Programmer's Reference* "を参照してください。  
  
### DAO 例外に使用するエラー コード  
 DAO の例外に対して、より多くの情報が広く利用できます。  [CDaoException](../mfc/reference/cdaoexception-class.md) のキャッチ オブジェクトの 3 個のデータ メンバーを介してエラー情報にアクセスする:  
  
-   [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) は データベースに関連付けられた DAO の Error オブジェクトのコレクションのエラー情報をカプセル化する [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) オブジェクトへのポインターが格納されます。  
  
-   [m\_nAfxDaoError](../Topic/CDaoException::m_nAfxDaoError.md) は MFC DAO クラスから拡張エラー コードが含まれています。  フォーム **AFX\_DAO\_ERROR\_XXX**の名前が、これらのエラー コードを `CDaoException`のデータ メンバーで説明しています。  
  
-   [m\_scode](../Topic/CDaoException::m_scode.md) は DAO の OLE `SCODE` を、該当する場合があります。  しかし、このエラー コードを使用する必要はありません。  通常、より多くの情報が他の 2 種類のデータ メンバーで使用できます。  `SCODE` 値の詳細については、"データ メンバーを参照してください。  
  
 DAO のエラー、DAO のエラー オブジェクト型と DAO のエラー コレクションについての追加情報が [CDaoException](../mfc/reference/cdaoexception-class.md)クラスで使用できます。  
  
##  <a name="_core_a_database_exception.2d.handling_example"></a> データベースの Exception Handling の例  
 次の例では [CRecordset](../Topic/CRecordset%20Class.md)\- **new** の演算子を使用してヒープの派生オブジェクト\) を作成し、レコードセットを開くされます \(ODBC データ ソースの場合\)。  DAO クラスの同様の例については、「DAO 例外例」を参照してください。  
  
### ODBC の例外の例  
 [開く](../Topic/CRecordset::Open.md) のメンバー関数は **try** ブロックを使用して **開く** の呼び出し \(ODBC クラスの型 [CDBException](../mfc/reference/cdbexception-class.md)\) のため、このコードで例外をスローすることができます。  **catch** 内の後続のブロックは `CDBException`をキャッチします。  例外オブジェクト自体を、`e`と呼ばれるチェックできますが、この場合はレコードセットを作成するには、操作が失敗したことを確認するだけです。  **catch** ブロックはメッセージ ボックスを表示し、レコードセット オブジェクトを削除して、クリーンアップします。  
  
 [!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/CPP/exceptions-database-exceptions_1.cpp)]  
  
### DAO 例外の例  
 DAO と ODBC の例の例に似ていますが、通常は、多くの種類の情報を取得できます。  次のコードは、レコードセットを開くとき。  この試みが例外をスローすれば、エラー情報の例外オブジェクトのデータ メンバーを確認できます。  前の ODBC の例と同様に、完全に、レコードセットを作成するには、操作が失敗したことを確認します。  
  
 [!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/CPP/exceptions-database-exceptions_2.cpp)]  
  
 このコードは、例外オブジェクトの [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) のメンバーからエラー メッセージの文字列を取得します。  MFC は、例外をスローすると、このメンバーを塗りつぶします。  
  
 エラー情報の詳細については `CDaoException` オブジェクトによって返される、クラスに [CDaoException](../mfc/reference/cdaoexception-class.md) と [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md)を参照します。  
  
 Microsoft Jet の ODBC を使っている場合 \(.mdb\) データベースを使用すると、ほとんどの場合は、一つの 1 つがエラー オブジェクトがあります。  まれなケースで ODBC データ ソースを使用して、複数のエラーがある場合、[CDaoException::GetErrorCount](../Topic/CDaoException::GetErrorCount.md)が返すエラーの数に基づいて DAO のエラー コレクションを反復処理できます。  ループを使用して `m_pErrorInfo` のデータ メンバーを再設定する呼び出し [CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md) たび。  
  
## 参照  
 [例外処理](../mfc/exception-handling-in-mfc.md)