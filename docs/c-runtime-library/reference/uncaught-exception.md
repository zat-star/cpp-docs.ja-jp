---
title: __uncaught_exception | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __uncaught_exception
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
f1_keywords: __uncaught_exception
dev_langs: C++
helpviewer_keywords: __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25d2e84bb6d336b2e530b833252b2b4a05dce4e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|__uncaught_exception|eh.h|  
  
## <a name="see-also"></a>参照  
 [try、throw、catch ステートメント (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)