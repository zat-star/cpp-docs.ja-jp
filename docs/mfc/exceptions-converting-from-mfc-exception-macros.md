---
title: "例外処理 : 古いコードの変換 | Microsoft Docs"
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
  - "catch ブロック, 区切り"
  - "CException クラス, 削除 (CException クラス オブジェクトを)"
  - "変換, コード (MFC マクロで記述された)"
  - "変換の例外"
  - "例外処理, 変換の例外"
  - "例外オブジェクト"
  - "例外オブジェクト, 削除"
  - "例外, 変換"
  - "例外, 削除 (例外オブジェクトを)"
  - "キーワード [C++], マクロ"
  - "マクロ, C++ のキーワード"
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 例外処理 : 古いコードの変換
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これは高度なトピックです。  
  
 ここでは、C\+\+ 例外処理 **try**キーワード、**catch**と `throw`を使用するには、Microsoft Foundation Class **TRY**—マクロ、**CATCH**、**THROW**記述された既存のコードに変換する方法をなど\) について説明します。  ここでは、次の内容について説明します。  
  
-   [変換の利点](#_core_advantages_of_converting)  
  
-   [例外処理マクロのコードの C\+\+ 例外処理機構を使用するように変換](#_core_doing_the_conversion)  
  
##  <a name="_core_advantages_of_converting"></a> 変換の利点  
 MFC バージョン 3.0 のマクロ実装と旧バージョンの実装の違いについて意識する必要がある場合は、既存のコードに変換する必要はありません。  コード実行の違いとそれ以降の変更は [例外: バージョン 3.0 の Exception Macros への変更](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)で説明します。  
  
 変換の主な利点は次のとおりです。:  
  
-   コードは、わずかに小さい .EXE または .DLL に対して C\+\+ 例外処理キーワードをコンパイルするために使用できます。  
  
-   C\+\+ 例外処理キーワードは、より幅広い用途: そのクラス `CException` にのみ例外処理マクロとクラスがそのクラスから派生した場合、\(`int`、**float**、`char`など\) コピーできる任意のデータ型の例外を処理できます。  
  
 マクロとキーワードとの主な違いは例外がスコープ外に出るとマクロを使用して、コードが「自動的に」キャッチされた例外を削除します。  キーワードを使用するコードでは、ため、明示的にキャッチした例外を削除する必要があります。  詳細については、記事 [例外: 例外をキャッチするか、または削除します。](../mfc/exceptions-catching-and-deleting-exceptions.md)を参照します。  
  
 もう一つの相違点は、構文です。  マクロとキーワードの構文は、3 種類の点で異なって:  
  
1.  マクロ引数と例外宣言:  
  
     **CATCH** のマクロの呼び出しに次の構文があります:  
  
     **CATCH\(**の *exception\_class*、*exception\_object\_pointer\_name* \#\#\#\)  
  
     クラス名とオブジェクト ポインター名の間にコンマを確認します。  
  
     **catch** キーワードの例外宣言は、この構文を使用して T:  
  
     **catch\(**の *exception\_type の* *exception\_name*\#\#\#\)  
  
     この例外の宣言ステートメントは、例外の型を catch ブロックで処理されます。  
  
2.  catch ブロックの限界:  
  
     マクロによっては、**CATCH** マクロ \(引数を使用\) 最初の catch ブロックを開始します; `AND_CATCH` マクロは、その後に続く catch ブロックを開始し、`END_CATCH` マクロは、catch ブロックのシーケンスを終了します。  
  
     キーワードによって、**catch** キーワード \(例外宣言を使用する\) 各 catch ブロックを開始します。  対応するメソッドは `END_CATCH` マクロはありません; 右中かっこ \(}\) を持つ catch ブロックを終了します。  
  
3.  throw 式:  
  
     マクロが再スローに `THROW_LAST` を現在の例外を使用します。  `throw` キーワードは、引数なしで、同じ効果があります。  
  
##  <a name="_core_doing_the_conversion"></a> 変換が行われます。  
  
#### コードを C\+\+ 例外処理キーワードを使用するマクロを使用して変換します。  
  
1.  MFC マクロ **TRY**、**CATCH**、`AND_CATCH`、`END_CATCH`、**THROW**と `THROW_LAST`のすべての一致を検索します。  
  
2.  次のマクロのすべてのインスタンスを、置換、または削除する:  
  
     **TRY** \(**try**に置き換えます。\)  
  
     **CATCH** \(**catch**に置き換えます。\)  
  
     `AND_CATCH` \(**catch**に置き換えます。\)  
  
     `END_CATCH` \(削除\)。  
  
     **THROW** \(`throw`に置き換えます。\)  
  
     `THROW_LAST` \(`throw`に置き換えます。\)  
  
3.  有効な例外宣言を形成するためにマクロ引数を変更します。  
  
     たとえば、変更します。  
  
     [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/CPP/exceptions-converting-from-mfc-exception-macros_1.cpp)]  
  
     から  
  
     [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/CPP/exceptions-converting-from-mfc-exception-macros_2.cpp)]  
  
4.  必要に応じて例外オブジェクトを削除するには、catch ブロックのコードを変更します。  詳細については、記事 [例外: 例外をキャッチするか、または削除します。](../mfc/exceptions-catching-and-deleting-exceptions.md)を参照します。  
  
 例外処理コードの例は、マクロ ベースの例外処理機構を使用して次のようになります。  次のコード例では、マクロを使用すると、例外 `e` は自動的に削除されることを確認する:  
  
 [!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/CPP/exceptions-converting-from-mfc-exception-macros_3.cpp)]  
  
 次のコード例では、C\+\+ の exception キーワードを使用するため、例外を明示的に削除する必要があります:  
  
 [!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/CPP/exceptions-converting-from-mfc-exception-macros_4.cpp)]  
  
 詳細については、「[例外: MFC マクロと C\+\+ 例外を使用する](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)」を参照してください。  
  
## 参照  
 [例外処理](../mfc/exception-handling-in-mfc.md)