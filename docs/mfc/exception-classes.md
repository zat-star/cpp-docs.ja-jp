---
title: "例外クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "例外クラス"
  - "例外処理, 例外クラス"
  - "MFC, 例外"
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 例外クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス ライブラリはクラス `CException`に基づいた例外処理機能を提供します。  アプリケーション フレームワークはコードで例外を使用して; また、でも使用できます。  詳細については、記事 [例外](../mfc/exception-handling-in-mfc.md)を参照します。  `CException`から独自の例外を派生できます。  
  
 MFC では、サポートするすべての例外の独自の例外、または例外クラスを派生する例外クラスを提供します。  
  
 [CException](../mfc/reference/cexception-class.md)  
 例外の基本クラスです。  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 アーカイブの例外。  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 例外 DAO データベース操作の失敗になります。  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 例外の ODBC データベースの処理でエラーが発生します。  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 ファイル中心例外。  
  
 [CMemoryException](../mfc/reference/cmemoryexception-class.md)  
 メモリ不足の例外。  
  
 [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)  
 例外にサポートされていない機能を使用して実行されます。  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE の例外処理でエラーが発生します。  このクラスは、コンテナーとサーバーの両方で使用されます。  
  
 [COleDispatchException](../Topic/COleDispatchException%20Class.md)  
 例外オートメーション中にエラーが発生します。  オートメーションの例外は、オートメーション サーバーでスローされ、オートメーション クライアントによってキャッチされます。  
  
 [CResourceException](../mfc/reference/cresourceexception-class.md)  
 例外 Windows リソースを読み込む場合に発生します。  
  
 [CUserException](../mfc/reference/cuserexception-class.md)  
 ユーザーが起動するアクションの停止に使用される例外です。  通常、ユーザーは問題のこの例外がスローされる前に知らせられました。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)