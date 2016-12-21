---
title: "ASSERT に代わる VERIFY の使用 | Microsoft Docs"
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
  - "assert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ASSERT ステートメント"
  - "アサーション, デバッグ"
  - "アサーション, トラブルシューティング (ASSERT ステートメントの)"
  - "デバッグ [MFC], ASSERT ステートメント"
  - "デバッグ (アサーションを)"
  - "VERIFY マクロ"
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ASSERT に代わる VERIFY の使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

デバッグ バージョンの MFC アプリケーションを実行しても問題がない場合でも、  同じアプリケーションのリリース バージョンでは、クラッシュしたり、間違った結果を返したり、それ以外の異常な動作が発生したりする場合があります。  
  
 正しく動作するかどうかを確認するために ASSERT ステートメントに重要なコードを入れたことが原因で、この問題が発生することがあります。  MFC プログラムのリリース ビルドでは ASSERT ステートメントがコメント化されるため、リリース ビルドではこのコードは実行されません。  
  
 関数呼び出しが成功することを確認するために ASSERT を使用している場合は、代わりに [VERIFY](../Topic/VERIFY.md) を使用してください。  VERIFY マクロは、アプリケーションのデバッグ ビルドとリリース ビルドの両方でその引数を評価します。  
  
 別の方法として、関数の戻り値を一時的な変数に代入して、ASSERT ステートメントで変数をテストすることもできます。  
  
 次のコードを例に取ります。  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 このコードは、デバッグ バージョンの MFC アプリケーションでは問題なく動作します。  `calloc( )` の呼び出しが失敗すると、ファイルと行番号を示す診断メッセージが表示されます。  しかし、リリース ビルドの MFC アプリケーションでは、次の状態になります。  
  
-   `calloc( )` の呼び出しは行われず、`buf` は初期化されない。  
  
-   `strcpy_s( )` が "`Hello, World`" をランダムなメモリにコピーし、アプリケーションがクラッシュしたりシステムの応答が停止したりする。  
  
-   `free()` が、割り当てられていないメモリを解放しようとする。  
  
 ASSERT を正しく使用するには、上記のコードを次のように変更する必要があります。  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );  
ASSERT( buf != NULL );  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 または、代わりに VERIFY を使用できます。  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
## 参照  
 [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)