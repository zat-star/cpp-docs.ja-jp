---
title: "___setlc_active_func、___unguarded_readlc_active_add_func | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
dev_langs:
- C++
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 08cda2e2b3f04663f3435ac9259117d54de80beb
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="setlcactivefunc-unguardedreadlcactiveaddfunc"></a>___setlc_active_func、___unguarded_readlc_active_add_func
互換性のために残されています。 バイナリの互換性を維持するためにのみ、これらの内部関数は CRT によってエクスポートされます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
int ___setlc_active_func(void);  
int * ___unguarded_readlc_active_add_func(void);  
```  
  
## <a name="return-value"></a>戻り値  
 戻される値は重要ではありません。  
  
## <a name="remarks"></a>コメント  
 内部 CRT 関数 `___setlc_active_func` および `___unguarded_readlc_active_add_func` は互換性のために残されており、使用されなくなりましたが、バイナリの互換性を維持するために CRT ライブラリによってエクスポートされます。 `___setlc_active_func` の本来の目的は、`setlocale` 関数の現在アクティブな呼び出しの数を返すことでした。 `___unguarded_readlc_active_add_func` の本来の目的は、ロケールをロックしないで参照した関数の数を返すことでした。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|none|  
  
## <a name="see-also"></a>関連項目  
 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
