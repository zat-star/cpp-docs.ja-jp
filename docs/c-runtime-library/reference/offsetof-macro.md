---
title: "offsetof マクロ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
f1_keywords: offsetof
dev_langs: C++
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 47243b64519540397573a47180dca5eed25f4c57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`offsetof`|\<stddef.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>関連項目  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)