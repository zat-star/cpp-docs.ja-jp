---
title: "_set_abort_behavior | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_abort_behavior"
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
  - "_set_abort_behavior"
  - "set_abort_behavior"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_abort_behavior 関数"
  - "中止 (プログラムを)"
  - "set_abort_behavior 関数"
ms.assetid: 43918766-e4ba-4b1f-80e8-1a4a910cd452
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# _set_abort_behavior
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラムが異常終了した場合に実行するアクションを指定します。  
  
> [!NOTE]
>  テスト シナリオまたはデバッグ シナリオの場合を除き、`abort` 関数を使用して [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリをシャットダウンしないでください。  プログラムや UI によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリを終了する方法は、「[Windows 8 アプリの認定の要件](http://go.microsoft.com/fwlink/?LinkId=262889)」により禁止されています。  詳細については、「[アプリケーションのライフサイクル \(Windows ストア アプリ\)](http://go.microsoft.com/fwlink/?LinkId=262853)」を参照してください。  
  
## 構文  
  
```  
unsigned int _set_abort_behavior(  
   unsigned int flags,  
   unsigned int mask  
);  
```  
  
#### パラメーター  
 \[入力\] `flags`  
 `abort` フラグの新しい値。  
  
 \[入力\] `mask`  
 設定する `abort` フラグのビットのマスク。  
  
## 戻り値  
 フラグの元の値。  
  
## 解説  
 `abort` フラグには、`_WRITE_ABORT_MSG` と `_CALL_REPORTFAULT` の 2 つの種類があります。  `_WRITE_ABORT_MSG` は、プログラムが異常終了したときに説明のテキスト メッセージを出力するかどうかを指定します。  メッセージは、アプリケーションが `abort` の関数を呼び出したことを示します。  既定の動作はメッセージを表示することです。  `_CALL_REPORTFAULT` が設定されていると、`abort` が呼び出されたときにワトソン クラッシュ ダンプが生成され、報告されます。  既定では、クラッシュ ダンプのレポートは、非デバッグ ビルドで有効になっています。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_set_abort_behavior`|\<stdlib.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```c  
// crt_set_abort_behavior.c  
// compile with: /TC  
#include <stdlib.h>  
  
int main()  
{  
   printf("Suppressing the abort message. If successful, this message"  
          " will be the only output.\n");  
   // Suppress the abort message  
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);  
   abort();  
}  
```  
  
  **中止メッセージを抑制しています。  成功した場合、このメッセージだけが出力されます。**    
## 参照  
 [abort](../../c-runtime-library/reference/abort.md)