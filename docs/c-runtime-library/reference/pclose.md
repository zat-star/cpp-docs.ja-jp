---
title: _pclose | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _pclose
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _pclose
- pclose
dev_langs: C++
helpviewer_keywords:
- _pclose function
- pclose function
- pipes, closing
ms.assetid: e2e31a9e-ba3a-4124-bcbb-c4040110b3d3
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 13609bbe4dae9b493b8467fd0ac9fe7d1437fa83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="pclose"></a>_pclose
新しいコマンド プロセッサを待機し、関連するパイプのストリームを閉じます。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int _pclose(  
FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 前回 `_popen` を呼び出したときの値を返します。  
  
## <a name="return-value"></a>戻り値  
 エラーが発生した場合は、終了するコマンド プロセッサ、または-1 の終了ステータスを返します。 戻り値の形式は、上位バイトと下位バイトが交換されることを除いて `_cwait` と同じです。 ストリームが **NULL** の場合、`_pclose` は `errno` を `EINVAL` に設定し、-1 を返します。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `_pclose` 関数は、関連する `_popen` の呼び出しによって開始されたコマンド プロセッサ (Cmd.exe) のプロセス ID を検索し、新しいコマンド プロセッサの [_cwait](../../c-runtime-library/reference/cwait.md) の呼び出しを実行して関連するパイプのストリームを閉じます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_pclose`|\<stdio.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>関連項目  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [_pipe](../../c-runtime-library/reference/pipe.md)   
 [_popen、_wpopen](../../c-runtime-library/reference/popen-wpopen.md)