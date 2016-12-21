---
title: "アサーションとユーザー指定のメッセージ (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "#error%2C assert%2C static_assert [C++]"
  - "ユーザーが指定したメッセージ [C++], コンパイル時"
  - "ユーザーが指定したメッセージ [C++], プリプロセッサ時間"
  - "ユーザーが指定したメッセージ [C++], 実行時に"
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# アサーションとユーザー指定のメッセージ (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 言語では、アプリケーションのデバッグに役立つ 3 つのエラー処理機構、つまり [\#error ディレクティブ](../preprocessor/hash-error-directive-c-cpp.md)、[static\_assert](../cpp/static-assert.md) キーワード、および [assert マクロ、\_assert、\_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) マクロがサポートされます。  3 つの機構すべてはエラー メッセージを発行し、2 つはソフトウェアのアサーションもテストします。  ソフトウェアのアサーションは、プログラムの特定位置にある true となるはずの条件を指定します。  コンパイル時にアサーションが失敗した場合、コンパイラで診断メッセージが発行され、コンパイル エラーが発生します。  ランタイムのアサーションが失敗した場合、オペレーティング システムで診断メッセージが発行され、アプリケーションを終了します。  
  
## 解説  
 アプリケーションの有効期間は、プリプロセス、コンパイル、および実行時フェーズで構成されます。  各エラー処理機構は、これらのいずれかのフェーズで使用できるデバッグ情報にアクセスします。  効果的にデバッグするには、そのフェーズに関する適切な情報を提供する機能を選択します:  
  
-   [\#error ディレクティブ](../preprocessor/hash-error-directive-c-cpp.md)は、プリプロセス時に有効です。  これは無条件にユーザー指定のメッセージを出力し、コンパイルはエラーで失敗します。  メッセージは、プリプロセッサ ディレクティブが操作するテキストを含むことができますが、結果の式は評価されません。  
  
-   [static\_assert](../cpp/static-assert.md) の宣言は、コンパイル時に有効になります。  これはブール型に変換できるユーザー指定の整数式で表されるソフトウェアのアサーションをテストします。  式がゼロ \(false\) に評価されると、ユーザー指定のメッセージが表示され、コンパイルはエラーで失敗します。  
  
     `static_assert` の宣言は、テンプレート引数をユーザー指定の式に含めることができるため、テンプレートをデバッグする場合に特に便利です。  
  
-   [assert マクロ、\_assert、\_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) マクロは、実行時に有効になります。  ユーザーが指定した式が評価され、結果がゼロの場合、システムは診断メッセージを発行し、アプリケーションを閉じます。  [\_ASSERT](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)、`_ASSERTE` など、その他のマクロは、このマクロと似ていますが、システムまたはユーザーによって定義されているさまざまな診断メッセージを出力します。  
  
## 参照  
 [\#error ディレクティブ](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert マクロ、\_assert、\_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [\_ASSERT、\_ASSERTE、\_ASSERT\_EXPR マクロ](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)   
 [static\_assert](../cpp/static-assert.md)   
 [\_STATIC\_ASSERT マクロ](../c-runtime-library/reference/static-assert-macro.md)   
 [テンプレート](../Topic/Templates%20\(C++\).md)