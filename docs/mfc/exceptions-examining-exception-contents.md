---
title: "例外処理 : 例外の内容の調査 | Microsoft Docs"
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
  - "catch ブロック, MFC 関数の例外"
  - "CException クラス, クラスの例外"
  - "例外処理, MFC"
  - "スロー (例外を), 例外の内容"
  - "try-catch 例外処理, 例外の内容"
  - "try-catch 例外処理, MFC 関数の例外"
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 例外処理 : 例外の内容の調査
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**catch** ブロックの引数がほとんどデータ型ですが、MFC 関数は `CException`クラスから派生される型の例外をスローします。  MFC 関数によってスローされると、例外をキャッチするには、引数を `CException` オブジェクトである **catch** のブロックを作成します \(または `CMemoryException`など、`CException`から派生されるオブジェクト\) へのポインター。  例外の厳密な型には、例外の原因に関する情報を収集するへの例外オブジェクトのデータ メンバーを確認できます。  
  
 たとえば、`CFileException` の型にファイル例外の理由を指定する列挙型を含む `m_cause` のデータ メンバーが含まれています。  有効な戻り値の例を **CFileException::fileNotFound** と **CFileException::readOnly**です。  
  
 次の例に `CFileException`の内容をチェックする方法を示します。  他の種類の例外も調べることができます。  
  
 [!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/CPP/exceptions-examining-exception-contents_1.cpp)]  
  
 詳細については、「[例外: 例外オブジェクトの解放](../Topic/Exceptions:%20Freeing%20Objects%20in%20Exceptions.md) と [例外: 例外をキャッチするか、または削除します。](../mfc/exceptions-catching-and-deleting-exceptions.md)」を参照してください。  
  
## 参照  
 [例外処理](../mfc/exception-handling-in-mfc.md)