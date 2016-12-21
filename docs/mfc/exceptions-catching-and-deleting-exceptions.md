---
title: "例外処理 : 例外のキャッチと削除 | Microsoft Docs"
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
  - "AND_CATCH マクロ"
  - "catch ブロック, キャッチと削除 (例外を)"
  - "例外処理, キャッチと削除 (例外を)"
  - "例外, 削除"
  - "実行, 戻る (catch ブロック内から)"
  - "try-catch 例外処理, キャッチと削除 (例外を)"
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 例外処理 : 例外のキャッチと削除
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の手順と例は、例外をキャッチして削除する方法を説明します。  **try**、**catch**と `throw` キーワードの詳細については、「[C\+\+ Exception Handling](../cpp/cpp-exception-handling.md)」を参照してください。  
  
 例外ハンドラーをそのコードが例外をキャッチするたびに例外を削除に失敗すると、メモリ リークが発生するため、処理する例外オブジェクトを削除する必要があります。  
  
 **catch** ブロックは次の場合に例外を削除する必要があります:  
  
-   **catch** ブロックは新しい例外をスローします。  
  
     。同じ例外を再びスローすれば、例外を削除する必要があります:  
  
     [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/CPP/exceptions-catching-and-deleting-exceptions_1.cpp)]  
  
-   **catch** ブロック内から実行を返します。  
  
> [!NOTE]
>  `CException`を削除した場合、例外を削除するに **削除** メンバー関数を使用します。  例外がヒープには失敗する可能性があるため、**delete** キーワードを使用しないでください。  
  
#### 例外をキャッチするか、または削除するには  
  
1.  **try** ブロックを設定するには **try** キーワードを使用します。  **try** ブロック内で例外をスローする可能性のあるプログラム ステートメントを実行します。  
  
     **catch** ブロックを設定するには **catch** キーワードを使用します。  **catch** ブロックに例外処理コードを記述します。  **catch** ブロックのコードが **try** ブロック内のコードが **catch** のステートメントで指定された型の例外をスローする場合にだけ実行されます。  
  
     次のスケルトンが **try** と **catch** ブロックが正常にどのように配置されるか:  
  
     [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/CPP/exceptions-catching-and-deleting-exceptions_2.cpp)]  
  
     例外がスローされると、例外宣言が例外の種類に一致する **catch** の最初のブロックへのコントロールのパス。  次に示すように **catch** の順次ブロックで例外の種類を処理する:  
  
     [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/CPP/exceptions-catching-and-deleting-exceptions_3.cpp)]  
  
 詳細については、「[例外: MFC Exception Macros からの変換](../mfc/exceptions-converting-from-mfc-exception-macros.md)」を参照してください。  
  
## 参照  
 [例外処理](../mfc/exception-handling-in-mfc.md)