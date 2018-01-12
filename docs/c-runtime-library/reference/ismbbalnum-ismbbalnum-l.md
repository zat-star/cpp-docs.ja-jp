---
title: "_ismbbalnum、_ismbbalnum_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbbalnum
- _ismbbalnum_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ismbbalnum
- ismbbalnum
- _ismbbalnum_l
- ismbbalnum_l
dev_langs: C++
helpviewer_keywords:
- _ismbbalnum_l function
- ismbbalnum function
- ismbbalnum_l function
- _ismbbalnum function
ms.assetid: 8025de50-a871-49fd-9ae6-f437b47aa987
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 830e86fad45d77a90fcc7ce22d484ad36d6b03b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ismbbalnum-ismbbalnuml"></a>_ismbbalnum、_ismbbalnum_l
指定されたマルチバイト文字が英字または数字かどうかを判定します。  
  
## <a name="syntax"></a>構文  
  
```  
int _ismbbalnum(  
   unsigned int c   
);  
int _ismbbalnum_l(  
   unsigned int c   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 テストする整数。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `_ismbbalnum` は、式が以下の場合に 0 以外の値を返します。  
  
```  
isalnum || _ismbbkalnum  
```  
  
 `c` の場合は 0 以外の値、それ以外の場合は 0 です。  
  
 これらの関数のうち `_l` サフィックスが付いているバージョンの同じ動作を実行しますが、ロケールに依存する動作に現在のロケールではなく渡されたロケールを使用するという点で異なります。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_ismbbalnum`|\<mbctype.h>|  
|`_ismbbalnum_l`|\<mbctype.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>参照  
 [バイト分類](../../c-runtime-library/byte-classification.md)   
 [_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)