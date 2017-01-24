---
title: "main に代わる wmain の使用 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "wmain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main 関数, wmain との比較"
  - "wmain 関数"
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# main に代わる wmain の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 Unicode プログラミング モデルでは、**main** 関数のワイド文字バージョンを定義できます。  Unicode 仕様に準拠した移植性のあるコードを作成する場合は、**main** ではなく **wmain** を使用します。  
  
 **wmain** に渡す仮引数は、**main** に渡す際の形式に準拠して宣言します。  さらに、ワイド文字の引数と、必要であればワイド文字環境ポインターもプログラムに渡すことができます。  wmain の引数 `argv` と `envp` の型は `wchar_t*` です。  
  
 プログラムが **main** 関数を使用している場合、マルチバイト文字環境は、プログラムの起動時にオペレーティング システムが作成します。  マルチバイト文字環境で使われるワイド文字のコピーは、必要に応じて作成されます \(たとえば、[\_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md) 関数や [\_wputenv](../c-runtime-library/reference/putenv-wputenv.md) 関数が呼び出されたとき\)。  `_wputenv` を最初に呼び出すとき、または MBCS 環境が既に存在する場合に `_wgetenv` を最初に呼び出すとき、対応するワイド文字列環境が作成され、その後は作成されたワイド文字列環境が `_wenviron` グローバル変数 \(`_environ` グローバル変数のワイド文字バージョン\) によって参照されます。  この時点までで、2 つの環境のコピー \(MBCS および Unicode\) が同時に存在していることになるわけですが、両方ともプログラムが消滅するまでオペレーティング システムによって保持されます。  
  
 同様に、プログラムが **wmain** 関数を使っている場合は、MBCS \(ASCII\) 環境が `_putenv` または `getenv` の最初の呼び出し時に作成され、また `_environ` グローバル変数によって環境のアドレスが示されます。  
  
 MBCS 環境の詳細については、「ランタイム ライブラリ リファレンス」の「[1 バイト文字セットとマルチバイト文字セット](../c-runtime-library/single-byte-and-multibyte-character-sets.md)」を参照してください。  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [main: プログラムの起動](../Topic/main:%20Program%20Startup.md)