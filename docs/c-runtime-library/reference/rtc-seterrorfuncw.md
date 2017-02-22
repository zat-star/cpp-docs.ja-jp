---
title: "_RTC_SetErrorFuncW | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_RTC_SetErrorFuncW"
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
  - "_RTC_SetErrorFuncW"
  - "RTC_SetErrorFuncW"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ランタイム エラー"
  - "RTC_SetErrorFuncW 関数"
  - "_RTC_error_fnW typedef"
  - "_RTC_SetErrorFuncW 関数"
  - "RTC_error_fnW typedef"
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _RTC_SetErrorFuncW
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

実行時エラー チェック \(RTC\) を報告するためのハンドラーとして関数を指定します。  
  
## 構文  
  
```  
  
_RTC_error_fnW _RTC_SetErrorFuncW(  
   _RTC_error_fnW  
 function   
);  
  
```  
  
#### パラメーター  
 `function`  
 実行時エラー チェックを処理する関数のアドレス。  
  
## 戻り値  
 以前に定義されたエラー関数。または、以前に定義された関数がない場合は `NULL`。  
  
## 解説  
 新しいコードでは `_RTC_SetErrorFuncW` のみを使用してください。`_RTC_SetErrorFunc` は、下位互換性のためにのみライブラリに含まれています。  
  
 `_RTC_SetErrorFuncW` コールバックは、リンクされたコンポーネントにのみ適用され、グローバルには適用されません。  
  
 `_RTC_SetErrorFuncW` に渡すアドレスが有効なエラー処理関数のアドレスであることを確認してください。  
  
 [\_RTC\_SetErrorType](../Topic/_RTC_SetErrorType.md) を使用して種類を \-1 に指定したエラーについては、エラー処理関数は呼び出されません。  
  
 この関数を呼び出すには、まず、実行時エラー チェックの初期化関数の 1 つを呼び出す必要があります。 詳細については、「[C ランタイム ライブラリなしのランタイム チェックの使用方法](../Topic/Using%20Run-Time%20Checks%20Without%20the%20C%20Run-Time%20Library.md)」を参照してください。  
  
 **\_RTC\_error\_fnW** は次のように定義されています。  
  
 **typedef int \(\_\_cdecl \*\_RTC\_error\_fnW\)\(int**  `errorType` **, const wchar\_t \*** *ファイル名* **, int**  *行番号* **, const wchar\_t \*** `moduleName` **, const wchar\_t \*** *format* **, ...\);**  
  
 それぞれの文字について以下に説明します。  
  
 `errorType`  
 [\_RTC\_SetErrorType](../Topic/_RTC_SetErrorType.md) で指定したエラーの種類。  
  
 *ファイル名*  
 障害が発生したソース ファイル。または、使用できるデバッグ情報がない場合は null。  
  
 *行番号*  
 障害が発生した*ファイル名*内の行番号。または、使用できるデバッグ情報がない場合は 0。  
  
 `moduleName`  
 この障害が発生した DLL 名または実行可能ファイル名。  
  
 *format*  
 残りのパラメーターを使用してエラー メッセージを表示するための printf スタイル文字列。 VA\_ARGLIST の最初の引数は、発生した RTC エラーの番号です。  
  
 **\_RTC\_error\_fnW** の使用方法を示す例については「[ネイティブ ランタイム チェックのカスタマイズ](../Topic/Native%20Run-Time%20Checks%20Customization.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_RTC_SetErrorFuncW`|\<rtcapi.h\>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [\_CrtDbgReport、\_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [ランタイム エラー チェック](../Topic/Run-Time%20Error%20Checking.md)