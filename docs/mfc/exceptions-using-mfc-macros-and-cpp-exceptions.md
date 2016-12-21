---
title: "例外処理 : MFC マクロと C++ 例外機構の使用 | Microsoft Docs"
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
  - "catch ブロック, 明示的な削除 (コードを)"
  - "catch ブロック, 同時使用"
  - "例外処理, MFC"
  - "例外処理, 混合言語"
  - "例外オブジェクト"
  - "例外オブジェクト, 削除"
  - "例外, MFC マクロと C++ キーワード"
  - "ヒープ破損"
  - "メモリ リーク, 例外オブジェクトが削除されない"
  - "入れ子になった catch ブロック"
  - "入れ子になった try ブロック"
  - "try-catch 例外処理, 同時使用 (MFC マクロと C++ キーワードの)"
  - "try-catch 例外処理, 入れ子になった try ブロック"
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 例外処理 : MFC マクロと C++ 例外機構の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、MFC の例外処理マクロと C\+\+ 例外処理キーワードの両方を使用するコードを記述するときの考慮事項について説明します。  
  
 ここでは、次のトピックについて説明します。  
  
-   [混乱の exception キーワードおよびマクロ](#_core_mixing_exception_keywords_and_macros)  
  
-   [catch ブロック内の Try ブロック](#_core_try_blocks_inside_catch_blocks)  
  
##  <a name="_core_mixing_exception_keywords_and_macros"></a> 混乱の exception キーワードおよびマクロ  
 同じプログラムのマクロ ベースの例外処理機構と C\+\+ 例外キーワードを使用できます。  ただし、例外処理キーワードを使用するコードは、スコープの外に出たときにマクロは、例外オブジェクトを自動的に削除するため、同じブロックの C\+\+ 例外キーワードと MFC マクロを混在させることはできません。  詳細については、記事 [例外: 例外をキャッチするか、または削除します。](../mfc/exceptions-catching-and-deleting-exceptions.md)を参照します。  
  
 マクロとキーワードとの主な違いは例外がスコープ外に出るとマクロが「自動的に」キャッチされた例外を削除します。  キーワードを使用するコードでは、; catch ブロックでキャッチされた例外を明示的に削除する必要があります。  例外が重複して削除されたりすると、例外オブジェクトが削除されない、またはヒープ破損のすると複合マクロと C\+\+ 例外はキーワード メモリ リークする。  
  
 次のコードは、例外のポインターを無効にします:  
  
 [!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/CPP/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]  
  
 問題は、実行が **CATCH** の「internal」ブロックから渡すとき `e` が削除されるためです。  **THROW** のステートメントの代わりに `THROW_LAST` マクロを使用して **CATCH** 「以外の」ブロックを有効なポインターを受け取るようにします:  
  
 [!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/CPP/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]  
  
##  <a name="_core_try_blocks_inside_catch_blocks"></a> Catch ブロック内の Try ブロック  
 再スロー **CATCH** ブロック内にある **try** ブロックから現在の例外中できません。  次の例は、無効です:  
  
 [!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/CPP/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]  
  
 詳細については、「[例外: 検証の例外の内容](../mfc/exceptions-examining-exception-contents.md)」を参照してください。  
  
## 参照  
 [例外処理](../mfc/exception-handling-in-mfc.md)