---
title: "スレッド コントロールのための C ランタイム ライブラリ関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_beginthread 関数"
  - "_beginthreadex 関数"
  - "_endthread 関数"
  - "_endthreadex 関数"
  - "マルチスレッド処理 [C++], 制御 (スレッドを)"
  - "スレッド処理 [C++], 制御 (スレッドを)"
ms.assetid: 39d0529c-c392-4c6f-94f5-105d1e8054e4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# スレッド コントロールのための C ランタイム ライブラリ関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Win32 プログラムはすべて、スレッドを少なくとも 1 つ持っています。  どのスレッドでも新しいスレッドを作成できます。  スレッドには、作業をすばやく完了して終了するものもあれば、プログラムの実行中アクティブ状態を続けるものもあります。  
  
 LIBCMT と MSVCRT の C ランタイム ライブラリには、スレッドの作成および終了用に [\_beginthread、\_beginthreadex](../Topic/_beginthread,%20_beginthreadex.md) 関数および [\_endthread、\_endthreadex](../Topic/_endthread,%20_endthreadex.md) 関数が用意されています。  
  
 `_beginthread` 関数および `_beginthreadex` 関数は、新しいスレッドを作成し、スレッドが正常に作成されるとスレッド識別子を返します。  スレッドは、実行を完了した時点で自動的に終了するか、`_endthread` または `_endthreadex` を呼び出すことによってそのスレッド自体を終了します。  
  
> [!NOTE]
>  Libcmt.lib を使用してビルドしたプログラムから C ランタイム ルーチンを呼び出す場合は、`_beginthread` 関数または `_beginthreadex` 関数でスレッドを起動する必要があります。  Win32 の `ExitThread` 関数および `CreateThread` 関数は使用しないでください。  また、C ランタイム ライブラリのデータ構造体へアクセス中のスレッドがあって、その完了を待っている複数のスレッドが存在する場合に `SuspendThread` を使うと、デッドロック状態になります。  
  
##  <a name="_core_the__beginthread_function"></a> \_beginthread 関数と \_beginthreadex 関数  
 `_beginthread` 関数および `_beginthreadex` 関数は、新しいスレッドを作成します。  スレッドは、プロセスのコードやデータ セグメントをプロセス内の他のスレッドと共有しますが、各スレッドには、独自のレジスタ値、スタック領域、および現在の命令アドレスがあります。  それぞれのスレッドに CPU 時間が与えられるので、プロセス中のすべてのスレッドを同時に実行できます。  
  
 `_beginthread` および `_beginthreadex` は、Win32 API の [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) 関数に似ていますが、次の違いがあります。  
  
-   これらの関数は、特定の C ランタイム ライブラリ変数を初期化します。  これは、スレッドで C ランタイム ライブラリを使う場合に重要です。  
  
-   `CreateThread` は、セキュリティ属性を制御します。  CreateThread を使うと、一時的に停止状態になっているスレッドの実行を再開できます。  
  
 `_beginthread` および `_beginthreadex` は、正常に終了した場合は新しいスレッドのハンドルを、エラーが発生した場合はエラー コードをそれぞれ返します。  
  
##  <a name="_core_the__endthread_function"></a> \_endthread 関数と \_endthreadex 関数  
 [\_endthread](../Topic/_endthread,%20_endthreadex.md) 関数は、`_beginthread` によって作成されたスレッドを終了します。同様に、`_endthreadex` は、`_beginthreadex` によって作成されたスレッドを終了します。  これらの関数が終了すると、スレッドは自動的に終了します。  `_endthread` および `_endthreadex` は、スレッドの内部条件に基づいて終了させる場合に便利です。  たとえば、通信ポートを制御できないときに、通信処理専用のスレッドを終了する場合があります。  
  
## 参照  
 [C と Win32 を使用するマルチスレッド](../parallel/multithreading-with-c-and-win32.md)