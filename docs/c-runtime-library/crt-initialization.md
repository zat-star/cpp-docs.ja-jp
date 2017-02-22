---
title: "CRT の初期化 | Microsoft Docs"
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
  - "CRT 初期化 [C++]"
ms.assetid: e7979813-1856-4848-9639-f29c86b74ad7
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# CRT の初期化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、CRT がネイティブ コードのグローバル状態を初期化する方法について説明します。  
  
 既定では、リンカー独自のスタートアップ コードを提供する CRT ライブラリが含まれています。  このスタートアップ コードはコンソール アプリケーションで CRT ライブラリ、呼び出しのグローバルの初期化子を初期化し、次にユーザーが指定した `main` 関数を呼び出します。  
  
## グローバル オブジェクトの初期化  
 次のコードがあるとします。  
  
```  
int func(void)  
{  
    return 3;  
}  
  
int gi = func();  
  
int main()  
{  
    return gi;  
}  
```  
  
 C\/C\+\+ の標準に従って、`func()` は `main()` が実行される前に呼び出す必要があります。  ただし、ユーザーがそれを呼び出します。  
  
 これを決定する 1 とおりの方法が `func()`にブレークポイントを設定し、アプリケーションをデバッグし、スタックをチェックします。  これは、CRT ソース・コードが Visual Studio に用意されているためです。  
  
 スタックの関数を参照する場合、検出したときに、それらの CRT が関数ポインターのリストをループして、それぞれを呼び出していることがわかります。  これらの関数は、クラス インスタンスの `func()` またはコンストラクターに似ています。  
  
 CRT は Visual C\+\+ コンパイラの関数ポインターのリストを取得します。  コンパイラはグローバルの初期化子を参照するとき、`CRT` がセクション名であり、`XCU` がグループ名\) `.CRT$XCU` セクションの動的な初期化子を生成します。   \(main.cpp と同様に、C の場合は.\)、C\+\+ ファイルとしてコンパイルすると、これらの動的な初期化子の一覧を取得するには **dumpbin \/all main.obj**コマンドを実行し、`.CRT$XCU` セクションを検索します。  これは次のようになります。:  
  
```  
SECTION HEADER #6  
.CRT$XCU name  
       0 physical address  
       0 virtual address  
       4 size of raw data  
     1F2 file pointer to raw data (000001F2 to 000001F5)  
     1F6 file pointer to relocation table  
       0 file pointer to line numbers  
       1 number of relocations  
       0 number of line numbers  
40300040 flags  
         Initialized Data  
         4 byte align  
         Read Only  
  
RAW DATA #6  
  00000000: 00 00 00 00                                      ....  
  
RELOCATIONS #6  
                                                Symbol    Symbol  
 Offset    Type              Applied To         Index     Name  
 --------  ----------------  -----------------  --------  ------  
 00000000  DIR32                      00000000         C  ??__Egi@@YAXXZ (void __cdecl `dynamic initializer for 'gi''(void))  
```  
  
 CRT は 2 個のポインターを定義する:  
  
-   『`.CRT$XCA`』の「`__xc_a`」  
  
-   『`.CRT$XCZ`』の「`__xc_z`」  
  
 グループの両方に `__xc_a` と `__xc_z`で定義されている他のシンボルがありません。  
  
 これで、リンカーは `.CRT` のさまざまなグループを読み込む場合、1 個のセクションでそれらを組み合わせて、アルファベット順に並べ替えます。  これは、Visual C\+\+ コンパイラが `.CRT$XCU`に配置\) ユーザー定義のグローバルな初期化子 `.CRT$XCA` の後に、`.CRT$XCZ`の前に常に送信されることを意味します。  
  
 セクションは次のようになります。:  
  
```  
.CRT$XCA  
            __xc_a  
.CRT$XCU  
            Pointer to Global Initializer 1  
            Pointer to Global Initializer 2  
.CRT$XCZ  
            __xc_z  
```  
  
 したがって、CRT ライブラリが `__xc_a` の両方を使用して、グローバル変数初期化子の開始と終了を確認 `__xc_z` はイメージが読み込まれた後、メモリに配置される方法に一覧表示されます。  
  
## 参照  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)