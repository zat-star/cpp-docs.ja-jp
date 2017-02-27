---
title: "_inp、_inpw、_inpd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _inp
- _inpw
- _inpd
apilocation:
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- inpd
- _inp
- _inpw
- _inpd
dev_langs:
- C++
helpviewer_keywords:
- inp function
- inpw function
- ports, I/O routines
- inpd function
- _inp function
- _inpd function
- I/O [CRT], port
- _inpw function
ms.assetid: 5d9c2e38-fc85-4294-86d5-7282cc02d1b3
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 54325f60b0d1714cab68f17152609a8980bc2a60

---
# <a name="inp-inpw-inpd"></a>_inp、_inpw、_inpd
ポートから&1; バイト (`_inp`)、1 ワード (`_inpw`)、または&1; ダブルワード (`_inpd`) のいずれかを読み込みます。  
  
> [!IMPORTANT]
>  これらは古い関数です。 Visual Studio 2015 以降では、CRT で使用できません。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 `port`  
 I/O ポート番号。  
  
## <a name="return-value"></a>戻り値  
 これらの関数は、 `port`から読み込んだバイト、ワード、またはダブルワードを返します。 エラーの戻り値はありません。  
  
## <a name="remarks"></a>コメント  
 `_inp`、 `_inpw`、 `_inpd` の各関数は、指定された入力ポートからそれぞれバイト、ワード、ダブルワードを&1; つ読み込みます。 ポート番号として、0 ～ 65,535 の unsigned short 型整数を入力できます。  
  
 これらの関数は I/O ポートから直接読み出すため、Windows NT、Windows 2000、Windows XP、および Windows Server 2003 のユーザー コードでは使用できない場合があります。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_inp`|\<conio.h>|  
|`_inpw`|\<conio.h>|  
|`_inpd`|\<conio.h>|  
  
 互換性の詳細については、「[互換性](../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [コンソール入出力とポート入出力](../c-runtime-library/console-and-port-i-o.md)   
 [_outp、_outpw、_outpd](../c-runtime-library/outp-outpw-outpd.md)


<!--HONumber=Feb17_HO4-->


