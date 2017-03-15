---
title: "関数またはマクロの選択に関する推奨事項 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.functions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "関数 [CRT], およびマクロ"
  - "マクロ, および関数"
ms.assetid: 18a633d6-cf1c-470c-a649-fa7677473e2b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 関数またはマクロの選択に関する推奨事項
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft のほとんどのランタイム ライブラリ ルーチンまたは作成された関数のコンパイルされますが、一部のルーチンは、マクロとして実装されます。  ヘッダー ファイルは、ルーチンの関数とマクロ環境の両方を宣言すると、マクロ定義は、関数宣言の後に常に表示される\) よりも優先されます。  関数とマクロとして実装されるルーチンを呼び出すと、コンパイラは 2 種類の方法で関数バージョンを使用するように強制できます:  
  
-   かっこ内の定期的な名前を囲みます。  
  
    ```  
    #include <ctype.h>  
    a = _toupper(a);    // Use macro version of toupper.  
    a = (_toupper)(a);  // Force compiler to use   
                        // function version of toupper.  
    ```  
  
-   `#undef` のディレクティブを持つマクロ定義を「undefined」:  
  
    ```  
    #include <ctype.h>  
    #undef _toupper  
    ```  
  
 ライブラリ ルーチンの関数とマクロ実装を選択する必要がある場合は、次の欠点を考慮する:  
  
-   **Speed versus size** は マクロを使用する主な利点実行を高速化する行です。  プリプロセス時に、マクロが使用されるたびに \(定義に置き換えて\) インライン展開されます。  関数定義が一度だけに関係なく回数が呼び出されたときに発生します。  マクロは、コード サイズが大きくなる可能性があると関数呼び出しのオーバーヘッドはありません。  
  
-   **関数の評価** A 関数は、アドレスに評価します; マクロは。  したがって、ポインターを必要とするコンテキストでマクロ名は使用できません。  たとえば、マクロに関数へのポインター、ポインターを宣言できます。  
  
-   関数を宣言すると、コンパイラは**Type\-checking** 引数の型をチェックできます。  マクロを宣言できないため、コンパイラはマクロ引数の型をチェックする; これは引数の数を確認できますが、マクロに渡されます。  
  
## 参照  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)