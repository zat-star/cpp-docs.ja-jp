---
title: "_fmode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "fmode"
  - "_fmode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ファイル変換 [C++]、既定のモード"
  - "fmode 関数"
  - "_fmode 関数"
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# _fmode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`_fmode` の変数は、テキストまたはバイナリ変換の既定のファイルの変換モードを設定します。  このグローバル変数はグローバル変数の代わりに使用する必要がある [\_set\_fmode](../c-runtime-library/reference/set-fmode.md)推奨されて、セキュリティを強化したバージョンについては [\_get\_fmode](../c-runtime-library/reference/get-fmode.md) 機能。  これは、Stdlib.h に次のように宣言されます。  
  
## 構文  
  
```  
extern int _fmode;  
```  
  
## 解説  
 `_fmode`の既定の設定は、テキスト モードの変換の `_O_TEXT`です。  `_O_BINARY`はバイナリ モードの設定です。  
  
 3 とおりの方法で `_fmode` の値を変更する:  
  
-   Binmode.obj のリンク。  これは `_O_BINARY`にすべてのファイルが発生 `_fmode` の初期設定により、以外 `stdin`、バイナリ モードで開く必要 `stdout`と `stderr` 変更します。  
  
-   `_fmode` のグローバル変数を取得または設定するに `_get_fmode` または `_set_fmode` に呼び出しを個別に作成します。  
  
-   プログラム内で設定して `_fmode` プロパティの値を変更します。直接。  
  
## 参照  
 [グローバル変数](../c-runtime-library/global-variables.md)   
 [\_get\_fmode](../c-runtime-library/reference/get-fmode.md)   
 [\_set\_fmode](../c-runtime-library/reference/set-fmode.md)