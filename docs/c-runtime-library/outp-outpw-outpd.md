---
title: "_outp、_outpw、_outpd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _outpd
- _outp
- _outpw
apilocation:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- _outpw
- _outpd
- _outp
- outpd
dev_langs: C++
helpviewer_keywords:
- outpw function
- words
- _outpd function
- outpd function
- outp function
- ports, writing bytes at
- bytes, writing to ports
- words, writing to ports
- double words
- double words, writing to ports
- _outpw function
- _outp function
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ac8f0cd386d8fece71f47b5c3d2048bead7cca1b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="outp-outpw-outpd"></a>_outp、_outpw、_outpd
1 バイト (`_outp`)、1 ワード (`_outpw`)、または 1 ダブルワード (`_outpd`) のいずれかをポートに出力します。  
  
> [!IMPORTANT]
>  これらは古い関数です。 Visual Studio 2015 以降では、CRT で使用できません。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int _outp(  
unsigned short port,  
int databyte   
);  
unsigned short _outpw(  
unsigned short port,  
unsigned short dataword   
);  
unsigned long _outpd(  
unsigned short port,  
unsigned long dataword   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *port*  
 ポート番号。  
  
 *databyte、dataword*  
 出力値。  
  
## <a name="return-value"></a>戻り値  
 関数は、出力データを返します。 エラーの戻り値はありません。  
  
## <a name="remarks"></a>コメント  
 `_outp`、 `_outpw`、 `_outpd` の各関数は、指定された出力ポートへそれぞれバイト、ワード、ダブルワードを 1 つ書き込みます。 *port* 引数は、0 - 65,535 の任意の符号なし整数です。 *databyte* は、0 - 255 の任意の整数です。*dataword* は、整数、符号なし短整数、および符号なし長整数の範囲の任意の値です。  
  
 これらの関数は I/O ポートへ直接書き出すため、Windows NT、Windows 2000、Windows XP、および Windows Server 2003 のユーザー コードでは使用できません。 これらのオペレーティング システムでの I/O ポートの使用方法については、MSDN で「Serial Communications in Win32 (Win32 のシリアル通信)」を検索してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_outp`|\<conio.h>|  
|`_outpw`|\<conio.h>|  
|`_outpd`|\<conio.h>|  
  
 互換性の詳細については、「[互換性](../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>関連項目  
 [コンソール入出力とポート入出力](../c-runtime-library/console-and-port-i-o.md)   
 [_inp、_inpw、_inpd](../c-runtime-library/inp-inpw-inpd.md)