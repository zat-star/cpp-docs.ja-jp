---
title: "下位入出力 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.io"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ファイル ハンドル [C++]"
  - "ファイル ハンドル [C++], I/O 関数"
  - "I/O [CRT], 関数"
  - "I/O [CRT], 下位"
  - "下位入出力ルーチン"
ms.assetid: 53e11bdd-6720-481c-8b2b-3a3a569ed534
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 下位入出力
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらの関数は、ストリーム入出力より低水準の操作のために、オペレーティング システムを直接呼び出します。  低水準入出力の呼び出しは、データのバッファリングや書式化を行いません。  
  
 プログラム起動時に開かれた標準ストリームに低水準入出力ルーチンでアクセスするには、次の定義済みファイル記述子を使用します。  
  
|Stream|ファイル記述子|  
|------------|-------------|  
|`stdin`|0|  
|`stdout`|1|  
|`stderr`|2|  
  
 低水準 I\/O ルーチンは、エラーが発生するとグローバル変数 [errno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) を設定します。  下位関数を使用する場合、STDIO.H で定義されている `EOF` \(end\-of\-file\) インジケーターなどの定数がプログラムで必要なときにだけ、STDIO.H をインクルードする必要があります。  
  
### 低水準入出力関数  
  
|関数|使用方法|  
|--------|----------|  
|[\_close](../Topic/_close.md)|ファイルを閉じます。|  
|[\_commit](../c-runtime-library/reference/commit.md)|ファイルをディスクにフラッシュします。|  
|[\_creat、\_wcreat](../c-runtime-library/reference/creat-wcreat.md)|ファイルを作成します。|  
|[\_dup](../c-runtime-library/reference/dup-dup2.md)|指定されたファイルに対して次に使用できるファイル記述子を返します。|  
|[\_dup2](../c-runtime-library/reference/dup-dup2.md)|指定されたファイルに対する第 2 の記述子を作成します。|  
|[\_eof](../c-runtime-library/reference/eof.md)|ファイルの終端をチェックします。|  
|[\_lseek、\_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)|ファイル ポインターを指定された位置に移動します。|  
|[\_open、\_wopen](../c-runtime-library/reference/open-wopen.md)|ファイルを開きます。|  
|[\_read](../Topic/_read.md)|ファイルからデータを読み込みます。|  
|[\_sopen、\_wsopen](../c-runtime-library/reference/sopen-wsopen.md)、[\_sopen\_s、\_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|共有モードでファイルを開きます。|  
|[\_tell、\_telli64](../c-runtime-library/reference/tell-telli64.md)|現在のファイル ポインターの位置を取得します。|  
|[\_umask](../c-runtime-library/reference/umask.md)、[\_umask\_s](../Topic/_umask_s.md)|ファイルのアクセス許可マスクを設定します。|  
|[\_write](../c-runtime-library/reference/write.md)|データをファイルに書き込みます。|  
  
 通常、`_dup` 関数と `_dup2` 関数は、定義済みファイル記述子を別のファイルに関連付けるために使用します。  
  
## 参照  
 [入出力](../Topic/Input%20and%20Output.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)   
 [システム コール](../Topic/System%20Calls.md)