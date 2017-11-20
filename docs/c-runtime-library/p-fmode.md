---
title: __p__fmode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __p__fmode
apilocation:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords: __p__fmode
dev_langs: C++
helpviewer_keywords: __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0a563385ecd1e773433e053cffbae24403eab6fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="pfmode"></a>__p__fmode
ファイルの入出力操作に対して既定の*ファイル変換モード*を指定する `_fmode` グローバル変数を指し示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
int* __p__fmode(  
   );  
```  
  
## <a name="return-value"></a>戻り値  
 `_fmode` グローバル変数へのポインター。  
  
## <a name="remarks"></a>コメント  
 `__p__fmode` 関数は内部使用専用であり、ユーザー コードから呼び出すことはできません。  
  
 ファイル変換モードは、[_open](../c-runtime-library/reference/open-wopen.md) および [_pipe](../c-runtime-library/reference/pipe.md) 入出力操作に対して `binary` または `text` の変換を指定します。 詳細については、「[_fmode](../c-runtime-library/fmode.md)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|__p\__fmode|stdlib.h|