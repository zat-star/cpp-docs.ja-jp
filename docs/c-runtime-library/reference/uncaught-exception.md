---
title: __uncaught_exception | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __uncaught_exception
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
apitype: DLLExport
f1_keywords:
- __uncaught_exception
dev_langs:
- C++
helpviewer_keywords:
- __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2b43a6b08087dcaeeda7959eaadbee9c250f4de9
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="uncaughtexception"></a>__uncaught_exception
1 つまたは複数の例外がスローされたが、[try-catch](../../cpp/try-throw-and-catch-statements-cpp.md) ステートメントの対応する `catch` ブロックによってまだ処理されていないことを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
bool __uncaught_exception(  
   );  
```  
  
## <a name="return-value"></a>戻り値  
 `try` ブロックで例外がスローされたときから、一致する `catch` ブロックが初期化されるまでの間は `true`、それ以外の場合は `false` です。  
  
## <a name="remarks"></a>コメント  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|__uncaught_exception|eh.h|  
  
## <a name="see-also"></a>関連項目  
 [try、throw、catch ステートメント (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)
