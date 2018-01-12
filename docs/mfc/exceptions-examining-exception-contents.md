---
title: "例外処理: 例外の内容の調査 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exception handling [MFC], MFC
- try-catch exception handling [MFC], MFC function exceptions
- catch blocks, MFC function exceptions
- CException class [MFC], class exceptions
- try-catch exception handling [MFC], exception contents
- throwing exceptions [MFC], exception contents
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 953dd61247f7d14ad04d5d5f85529c89f3aaad9d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-examining-exception-contents"></a>例外処理 : 例外の内容の調査
ただし、**キャッチ**ブロックの引数は、ほとんどのデータ型であることができます、MFC 関数がクラスから派生した型の例外をスロー`CException`です。 MFC 関数によってスローされる例外をキャッチするには、次に、記述する、**キャッチ**ブロックが、引数がポインターを`CException`オブジェクト (から派生したオブジェクトまたは`CException`など`CMemoryException`)。 例外の正確な型によっては、例外の原因を特定の情報を収集する例外オブジェクトのデータ メンバーを確認できます。  
  
 たとえば、`CFileException`型には、`m_cause`データ メンバーは、ファイルの例外の原因を示す列挙型が含まれています。 考えられる例をいくつかの戻り値は**CFileException::fileNotFound**と**CFileException::readOnly**です。  
  
 次の例の内容を確認する方法を示しています、`CFileException`です。 他の例外の種類は、同様に調査することができます。  
  
 [!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]  
  
 詳細については、次を参照してください。[例外: 例外処理でのオブジェクトの解放](../mfc/exceptions-freeing-objects-in-exceptions.md)と[例外: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)です。  
  
## <a name="see-also"></a>参照  
 [例外処理](../mfc/exception-handling-in-mfc.md)

