---
title: "_CrtMemCheckpoint | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtMemCheckpoint"
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
apitype: "DLLExport"
f1_keywords: 
  - "CrtMemCheckpoint"
  - "_CrtMemCheckpoint"
  - "crtdbg/_CrtMemCheckpoint"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CrtMemCheckpoint 関数"
  - "_CrtMemCheckpoint 関数"
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtMemCheckpoint
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

デバッグ ヒープの現在の状態を取得し、アプリケーションが指定した `_CrtMemState` 構造体に格納します \(デバッグ バージョンだけ\)。  
  
## 構文  
  
```  
void _CrtMemCheckpoint(  
   _CrtMemState *state   
);  
```  
  
#### パラメーター  
 `state`  
 メモリのチェックポイントを格納する `_CrtMemState` 構造体へのポインター。  
  
## 解説  
 `_CrtMemCheckpoint` 関数は、指定された時点のデバッグ ヒープの状態のスナップショットを作成します。[\_CrtMemDifference](../Topic/_CrtMemDifference.md) などの他のヒープ状態関数は、このスナップショットを使用してメモリ リークおよびその他の問題を検出できます。[\_DEBUG](../Topic/_DEBUG.md) が定義されていない場合、`_CrtMemState` の呼び出しは前処理で削除されます。  
  
 `_CrtMemState` パラメーターには、Crtdbg.h で定義されている `state` 構造体の割り当て済みインスタンスへのポインターを渡す必要があります。 チェックポイントの作成時に `_CrtMemCheckpoint` でエラーが発生すると、`_CRT_WARN` デバッグ レポートが生成され、問題が表示されます。  
  
 ヒープ状態関数と `_CrtMemState` 構造体について詳しくは、「[ヒープの状態をレポートする関数](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions)」をご覧ください。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「[CRT デバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」をご覧ください。  
  
 `state` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は [errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) を `EINVAL` に設定して処理を戻します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_CrtMemCheckpoint`|\<crtdbg.h\>、\<errno.h\>|  
  
 互換性について詳しくは、「はじめに」の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
 **ライブラリ:** UCRT のデバッグ バージョンのみ。  
  
## 同等の .NET Framework 関数  
 該当しない。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [\_CrtMemDifference](../Topic/_CrtMemDifference.md)