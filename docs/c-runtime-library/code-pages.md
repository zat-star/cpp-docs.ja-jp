---
title: "コード ページ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.international"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ANSI [C++], コード ページ"
  - "文字セット [C++], コード ページ"
  - "コード ページ [C++], 型"
  - "ロケール コード ページ [C++]"
  - "ローカリゼーション [C++], コード ページ"
  - "マルチバイト コード ページ [C++]"
  - "システム既定のコード ページ"
ms.assetid: 4a26fc42-185a-4add-98bf-a7b314ae6186
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コード ページ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`code page` 数は、区切り記号、およびそのほかのグリフを含む文字セットです。  言語およびロケールはコード ページを使用する場合があります。  たとえば、ANSI のコード ページ 1252 では英語やほとんどのヨーロッパ言語で使用される; OEM 932 のコード ページは、日本語の漢字で使用されます。  
  
 コード ページは、バイト値またはマルチバイト文字の値への割り当てとしてテーブルを表すことができます。  多くのコード ページは–範囲 0x00 ~ 0x7F の文字の ASCII 文字セットを共有します。  
  
 Microsoft ランタイム ライブラリ コードは、ページの型を使用する:  
  
-   システムの既定の ANSI コード ページ。  起動時に既定で、オペレーティング システムから取得したシステムの既定の ANSI コード ページにランタイム システムが自動的に、マルチバイトのコード ページを設定します。  呼び出し:  
  
    ```  
    setlocale ( LC_ALL, "" );  
    ```  
  
     また、システムの既定の ANSI コード ページにロケールを設定します。  
  
-   ロケールのコード ページ。  多数のランタイム ルーチンの動作は、ロケールのコード ページを含む現在のロケールの設定に依存しています。\(詳細については、「[ロケール依存ルーチン](../c-runtime-library/locale.md)」を参照してください。既定では、Microsoft ランタイム ライブラリのすべてのロケール依存ルーチン「C」ロケールに対応するコード ページが使用されます。  実行時に [setlocale](../Topic/setlocale,%20_wsetlocale.md)と使用中のロケールのコード ページを変更するか、呼び出すことができます。  
  
-   マルチバイトのコード ページ。  ランタイム ライブラリのマルチバイト文字ルーチンのほとんどの動作は現在のマルチバイトのコード ページの設定によって異なります。  既定では、次のルーチン システム既定 ANSI コード ページを使用します。  ランタイムで個別に [\_getmbcp](../c-runtime-library/reference/getmbcp.md) と [\_setmbcp](../c-runtime-library/reference/setmbcp.md)マルチバイトのコード ページを照会および変更できます。  
  
-   「C」ロケールでは、ANSI C プログラムが従来実行したロケールに対応するように定義されています。  「C」ロケール \(「C」コード ページ\) のコード ページは、ASCII 文字セットに対応します。  たとえば、「C」ロケールでは、`islower` 値 0x61 – 0x7A のみの場合に true を返します。  別のロケールでは、`islower` はそのロケールによって定義されるように、およびそのほかの値に対して true を返す場合があります。  
  
## 参照  
 [国際化](../c-runtime-library/internationalization.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)