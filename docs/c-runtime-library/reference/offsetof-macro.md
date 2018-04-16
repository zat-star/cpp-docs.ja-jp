---
title: "offsetof マクロ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
- offsetof
dev_langs:
- C++
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a70bb2823f29caf3f76224bfb91c3c9642bbdcf1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="offsetof-macro"></a>offsetof マクロ
親構造体の先頭からメンバーのオフセットを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      size_t offsetof(  
   structName,  
   memberName   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *structName*  
 親データ構造体の名前。  
  
 `memberName`  
 オフセットを決定する親データ構造体のメンバーの名前。  
  
## <a name="return-value"></a>戻り値  
 `offsetof` は、親データ構造体の先頭から、指定されたメンバーのオフセットをバイト単位で返します。 ビット フィールドには定義されません。  
  
## <a name="remarks"></a>コメント  
 `offsetof` マクロは、*structName* によって指定された構造体の先頭からバイト単位で数えた `memberName` のオフセットを、`size_t` 型の値として返します。 `struct` キーワードで型を指定できます。  
  
> [!NOTE]
>  `offsetof` は関数ではないため、C のプロトタイプを使用して記述することはできません。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`offsetof`|\<stddef.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)