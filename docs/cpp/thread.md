---
title: "スレッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "thread"
  - "thread_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++], スレッド"
  - "thread __declspec キーワード"
  - "スレッド ローカル ストレージ (TLS)"
  - "TLS (スレッド ローカル ストレージ), コンパイラの実装"
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# スレッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 **thread** 拡張ストレージ クラス修飾子は、スレッド ローカル変数を宣言するために使用されます。  C\+\+11 における移植可能な等価のものとして、[thread\_local](../cpp/storage-classes-cpp.md#thread_local) ストレージ クラス指定子を使用します。  
  
## 構文  
  
```  
  
__declspec( thread ) declarator  
```  
  
## 解説  
 スレッド ローカル ストレージ \(TLS\) は、特定のマルチスレッド プロセスの各スレッドが、スレッド固有のデータを格納するための場所を割り当てる機能です。  標準のマルチスレッド プログラムでは、データは特定のプロセスのすべてのスレッド間で共有されますが、スレッド ローカル ストレージはスレッドごとのデータを割り当てるための機能です。  スレッドの詳細については、[マルチスレッド](../parallel/multithreading-support-for-older-code-visual-cpp.md)に関するトピックを参照してください。  
  
 スレッド ローカル変数の宣言では、[拡張属性構文](../cpp/declspec.md)を使用し、`__declspec` キーワードを **thread** キーワードと共に使用する必要があります。  たとえば、次に示すコードは、整数型のスレッド ローカル変数を宣言して特定の値に初期化します。  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
 スレッド ローカルのオブジェクトおよび変数を宣言するときは、以下のガイドラインに従う必要があります。  
  
-   **thread** 属性は、クラスおよびデータの宣言と定義のみに適用できます。**thread** を関数宣言や関数定義に使用することはできません。  
  
-   **thread** 属性の使用は、DLL のインポートの[遅延読み込み](../build/reference/linker-support-for-delay-loaded-dlls.md)に干渉する可能性があります。  
  
-   XP システムでは、DLL が \_\_declspec\(thread\) のデータを使用して、データが LoadLibrary 経由で動的に読み込まれる場合、`thread` は正常に機能しないことがあります。  
  
-   **thread** 属性は、静的ストレージ存続期間のあるデータ項目にのみ指定できます。  これには、グローバルなデータ オブジェクト \(**static** と `extern` の両方\)、ローカルな静的オブジェクト、クラスの静的データ メンバーなどが含まれます。  **thread** 属性を使用して自動データ オブジェクトを宣言することはできません。  
  
-   宣言と定義が同じファイルと別々のファイルのどちらで発生する場合でも、スレッド ローカル オブジェクトの宣言と定義には **thread** 属性を使用する必要があります。  
  
-   **thread** 属性を型修飾子として使用することはできません。  
  
-   **thread** 属性を使用するオブジェクトの宣言は許可されるので、次の 2 つの例は同じ意味になります。  
  
    ```  
    // declspec_thread_2.cpp  
    // compile with: /LD  
    __declspec( thread ) class B {  
    public:  
       int data;  
    } BObject;   // BObject declared thread local.  
  
    class B2 {  
    public:  
       int data;  
    };  
    __declspec( thread ) B2 BObject2;   // BObject2 declared thread local.  
    ```  
  
-   標準 C では、自分自身への参照を含む式でオブジェクトや変数を初期化できます。ただし、この場合のオブジェクトは、非静的なものに限られます。  C\+\+ では、通常、自分自身への参照を含む式でこのようにオブジェクトを動的に初期化できますが、この種の初期化はスレッド ローカル オブジェクトでは許可されません。  例:  
  
    ```  
    // declspec_thread_3.cpp  
    // compile with: /LD  
    #define Thread __declspec( thread )  
    int j = j;   // Okay in C++; C error  
    Thread int tls_i = sizeof( tls_i );   // Okay in C and C++  
    ```  
  
     初期化されるオブジェクトが含まれる `sizeof` 式は、そのオブジェクト自体への参照が発生しないので、C と C\+\+ の両方で有効になります。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [スレッド ローカル ストレージ \(TLS: Thread Local Storage\)](../parallel/thread-local-storage-tls.md)