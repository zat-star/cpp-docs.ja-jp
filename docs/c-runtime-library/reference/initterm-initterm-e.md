---
title: "_initterm, _initterm_e | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_initterm_e"
  - "_initterm"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_initterm_e"
  - "initterm"
  - "_initterm"
  - "initterm_e"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "initterm 関数"
  - "initterm_e 関数"
  - "_initterm 関数"
  - "_initterm_e 関数"
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# _initterm, _initterm_e
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

テーブル関数ポインターを検索し、それらを初期化する内部メソッド。  
  
 最初のポインターはテーブルの開始位置で、2 番目のポインターは、完了の場所です。  
  
## 構文  
  
```  
void __cdecl _initterm(  
   PVFV *,  
   PVFV *  
);  
  
int __cdecl _initterm_e(  
   PVFV *,  
   PVFV *  
);  
```  
  
## 戻り値  
 初期化が失敗し、エラーをスローすれば以外のエラー コード; エラーが発生しなかった場合は 0。  
  
## 解説  
 これらのメソッドは、. C\/C\+\+ プログラムの初期化中に内部的に呼び出されます。  プログラムのこれらのメソッドを呼び出さないでください。  
  
 これらのメソッドはスタック ウォークが関数にテーブル、`NULL` エントリをスキップし、続行されます。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)