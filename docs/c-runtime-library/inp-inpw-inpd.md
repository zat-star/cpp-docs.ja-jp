---
title: "_inp、_inpw、_inpd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_inp"
  - "_inpw"
  - "_inpd"
apilocation: 
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "inpd"
  - "_inp"
  - "_inpw"
  - "_inpd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_inp 関数"
  - "_inpd 関数"
  - "_inpw 関数"
  - "I/O [CRT], ポート"
  - "inp 関数"
  - "inpd 関数"
  - "inpw 関数"
  - "ポート, I/O ルーチン"
ms.assetid: 5d9c2e38-fc85-4294-86d5-7282cc02d1b3
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _inp、_inpw、_inpd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ポートから 1 バイト \(`_inp`\)、1 ワード \(`_inpw`\)、または 1 ダブルワード \(`_inpd`\) のいずれかを読み込みます。  
  
> [!IMPORTANT]
>  これらは古い関数です。 Visual Studio 2015 以降、これらは CRT で使用できません。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _inp(   
   unsigned short port   
);  
unsigned short _inpw(   
   unsigned short port   
);  
unsigned long _inpd(   
   unsigned short port   
);  
```  
  
#### パラメーター  
 `port`  
 I\/O ポート番号。  
  
## 戻り値  
 これらの関数は、`port` から読み込んだバイト、ワード、またはダブルワードを返します。 エラーの戻り値はありません。  
  
## 解説  
 `_inp`、`_inpw`、`_inpd`の各関数は、指定された入力ポートからそれぞれバイト、ワード、ダブルワードを 1 つ読み込みます。 ポート番号として、0 ～ 65,535 の unsigned short 型整数を入力できます。  
  
 これらの関数は I\/O ポートから直接読み出すため、Windows NT、Windows 2000、Windows XP、および Windows Server 2003 のユーザー コードでは使用できない場合があります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_inp`|\<conio.h\>|  
|`_inpw`|\<conio.h\>|  
|`_inpd`|\<conio.h\>|  
  
 互換性の詳細については、「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [コンソール入出力とポート入出力](../c-runtime-library/console-and-port-i-o.md)   
 [\_outp、\_outpw、\_outpd](../Topic/_outp,%20_outpw,%20_outpd.md)