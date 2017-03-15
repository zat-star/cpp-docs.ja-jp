---
title: "__getmainargs、__wgetmainargs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__wgetmainargs"
  - "__getmainargs"
apilocation: 
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__wgetmainargs"
  - "__getmainargs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wgetmainargs"
  - "__getmainargs"
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# __getmainargs、__wgetmainargs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

解析するコマンド ラインを呼び出し、`main()` の戻るに渡されたポインターを通じて引数をコピーします。  
  
## 構文  
  
```cpp  
int __getmainargs(  
    int * _Argc,   
   char *** _Argv,   
   char *** _Env,   
   int _DoWildCard,  
_startupinfo * _StartInfo);  
  
 int __wgetmainargs (  
   int *_Argc,  
   wchar_t ***_Argv,  
   wchar_t ***_Env,  
   int _DoWildCard,  
   _startupinfo * _StartInfo)  
  
```  
  
#### パラメーター  
 `_Argc`  
 `argv`でない引数の数を含む整数。  `argc` パラメーターは 1.より大きいか等しい常に。  
  
 `_Argv`  
 プログラムにユーザーが入力したコマンド ライン引数を表す NULL で終わる文字列の配列。  規則では、`argv[0]` はプログラムを起動するコマンド argv 1 \[\]で最初のコマンド ライン引数など、常に NULL の argv \[\] argc までです。  最初のコマンド ライン引数 `argv[1]` は常に、最後の 1 つが `argv[argc – 1]`です。  
  
 `_Env`  
 変数を表す文字列の配列はユーザー環境で設定します。  この配列は空のエントリで終了します。  
  
 `_DoWildCard`  
 1 に設定するとコマンド ライン引数のワイルドカードを展開するか、0 に設定すると何もする整数。  
  
 `_StartInfo`  
 CRT DLL に渡す他の情報。  
  
## 戻り値  
 正常終了した場合は 0; 失敗した場合は負の値を返します。  
  
## 解説  
 非ワイド文字プラットフォームの `__getmainargs`、ワイド文字 \(Unicode\) プラットフォームの `__wgetmainargs` を使用します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|\_\_getmainargs|internal.h|  
|\_\_wgetmainargs|internal.h|