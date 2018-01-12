---
title: "_ _inbyte |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __inbyte
- __inbyte_cpp
dev_langs: C++
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 20781d2e8f925cec9bacb8ca125f68c3e9f7c201
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="inbyte"></a>__inbyte
**Microsoft 固有の仕様**  
  
 生成、`in`命令、1 バイトを返すことによって指定されたポートから読み取られた`Port`です。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char __inbyte(  
   unsigned short Port  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `Port`  
 読み取りにポートです。  
  
## <a name="return-value"></a>戻り値  
 指定されたポートから読み取られたバイト。  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__inbyte`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="remarks"></a>コメント  
 このルーチンは、組み込みとしてのみ使用できます。  
  
## <a name="see-also"></a>参照  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)