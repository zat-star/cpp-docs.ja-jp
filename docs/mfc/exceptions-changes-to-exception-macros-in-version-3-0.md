---
title: "例外処理 : MFC 3.0 での変更点 | Microsoft Docs"
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
  - "C++ 例外処理, アップグレードの考慮事項"
  - "CATCH マクロ"
  - "例外, 変更点"
  - "THROW_LAST マクロ"
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 例外処理 : MFC 3.0 での変更点
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これは高度なトピックです。  
  
 MFC バージョン 3.0 で C\+\+ 例外処理機構を使用するように以降、例外処理マクロは変更されました。  ここでは、これらの変更がマクロを使用する既存のコードの動作に影響する可能性があるかを示します。  
  
 ここでは、次のトピックについて説明します。  
  
-   [例外の種類と catch マクロ](#_core_exception_types_and_the_catch_macro)  
  
-   [例外を再スローすること](#_core_re.2d.throwing_exceptions)  
  
##  <a name="_core_exception_types_and_the_catch_macro"></a> 例外の種類と catch マクロ  
 以前のバージョンの MFC では、**CATCH** マクロは、例外の型を決定するために MFC の実行時の型情報を使用して; つまり、すべての種類の例外はキャッチ側で決定されるです。  ただし、C\+\+ 例外を除くすべての種類の例外がスローされる例外オブジェクトの型によってスロー サイトで決定されます。常になります。  これにより、スローされたオブジェクトへのポインターの型がスローされたオブジェクトの型と異なるまれなケースで非互換性の問題が発生します。  
  
 次の例では、MFC バージョン 3.0 と旧バージョンの違いの結果を示しています。:  
  
 [!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/CPP/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]  
  
 このコードは、バージョン 3.0 でコントロールが最初の **catch** に一致する例外宣言を除くブロックを常に渡すための動作が変わります。  throw 式の結果  
  
 [!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/CPP/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]  
  
 **CCustomException**として構築が、**CException\***としてスローされます。  実行時に型をテストする MFC バージョン 2.5 以前使用中 `CObject::IsKindOf` の **CATCH** マクロ。  式。  
  
 [!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/CPP/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]  
  
 true の場合、最初の catch ブロック Catch は例外です。  例外処理マクロの多くを実装するには、C\+\+ 例外処理を使用するバージョン 3.0 では、2 番目の catch ブロックがスローされた `CException`と一致します。  
  
 このようなコードは一般的ではありません。  通常は、例外オブジェクトがジェネリック **CException\***を受け入れる別の関数に実行処理する「Pre」スロー"をスローする例外を渡す場合に表示されます。  
  
 例外が発生すると、この問題を回避するには、throw 式を関数から呼び出し元のコードに移動し、コンパイラで認識される実際の型の例外をスローしてください。  
  
##  <a name="_core_re.2d.throwing_exceptions"></a> 例外を再スローすること  
 catch ブロックは、同じキャッチした例外のポインターをスローすることはできません。  
  
 たとえば、このコードは、以前のバージョンで有効ですが、バージョン 3.0 で予期しない結果があります:  
  
 [!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/CPP/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]  
  
 catch ブロックの **THROW** を使用して外側の Catch サイトが無効なポインターを受け取るようにポインター `e` を削除します。  再スロー `e`に `THROW_LAST` を使用します。  
  
 詳細については、「[例外: 例外をキャッチするか、または削除します。](../mfc/exceptions-catching-and-deleting-exceptions.md)」を参照してください。  
  
## 参照  
 [例外処理](../mfc/exception-handling-in-mfc.md)