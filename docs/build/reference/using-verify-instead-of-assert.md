---
title: "ASSERT に代わる VERIFY の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: assert
dev_langs: C++
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ffe046a281bbbbefc251b48df55ecd275515e60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-verify-instead-of-assert"></a>ASSERT に代わる VERIFY の使用
MFC アプリケーションのデバッグ バージョンを実行するときに問題がないとします。 ただし、同じアプリケーションのリリース バージョンがクラッシュした不適切な結果を返しますやは他のいくつかの異常な動作を示します。  
  
 この問題は、正しく動作することを確認する ASSERT ステートメントで重要なコードを配置するときに発生することができます。 ASSERT ステートメントは、MFC プログラムのリリース ビルドでコメント アウトされているため、コードは、リリース ビルドでは実行されません。  
  
 ASSERT 関数呼び出しが成功したことを確認するを使用している場合は、使用を検討して[を確認してください](../../mfc/reference/diagnostic-services.md#verify)代わりにします。 VERIFY マクロは、両方のデバッグで、自分の引数を評価し、アプリケーションのリリース ビルドをします。  
  
 手法は一時変数に関数の戻り値を代入し、ASSERT ステートメントで変数をテストする (推奨別)。  
  
 次のコード フラグメントを確認してください。  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 このコードは、MFC アプリケーションのデバッグ バージョンで完全に実行されます。 場合に呼び出し`calloc( )`失敗した場合、ファイルと行番号を含む診断メッセージが表示されます。 ただしでは、MFC アプリケーションの製品版ビルド。  
  
-   呼び出し`calloc( )`は決して行われず、まま`buf`初期化されていない、または  
  
-   `strcpy_s( )`コピー"`Hello, World`"ランダムなメモリ、場合によってはアプリケーションがクラッシュまたは原因でシステムが応答を停止するにまたは  
  
-   `free()`割り当てられていないメモリを解放しようとしています。  
  
 ASSERT を正しく使用するには、次のコード サンプルを変更する必要があります。  
  
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
  
 または、代わりに検証を使用することができます。  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
## <a name="see-also"></a>参照  
 [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)