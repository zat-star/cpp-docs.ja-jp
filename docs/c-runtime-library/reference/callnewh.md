---
title: _callnewh | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _callnewh
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords: _callnewh
dev_langs: C++
helpviewer_keywords: _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86085472c63d2ad3fbc1cf53d893bd8da2f8c244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="callnewh"></a>_callnewh
現在インストールされている*新しいハンドラー*を呼び出します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
int _callnewh(  
   size_t size  
   )  
```  
  
#### <a name="parameters"></a>パラメーター  
 `size`  
 [new 演算子](../../cpp/new-operator-cpp.md)が割り当てようとしたメモリの量。  
  
## <a name="return-value"></a>戻り値  
  
|[値]|説明|  
|-----------|-----------------|  
|0|エラー: 新しいハンドラーがインストールされていないか、新しいハンドラーがアクティブになっていません。|  
|1|成功: 新しいハンドラーがインストールされ、アクティブになっています。 メモリ割り当てを再試行できます。|  
  
## <a name="exceptions"></a>例外  
 *新しいハンドラー*が見つからない場合、[bad_alloc](../../standard-library/bad-alloc-class.md) をスローします。  
  
## <a name="remarks"></a>コメント  
 *新しいハンドラー*は、[new 演算子](../../cpp/new-operator-cpp.md)がメモリの割り当てに失敗した場合に呼び出されます。 新しいハンドラーは、後続の割り当てが成功するようにメモリを解放するなど、適切な処理を開始する場合があります。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|_callnewh|internal.h|  
  
## <a name="see-also"></a>参照  
 [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md)   
 [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md)