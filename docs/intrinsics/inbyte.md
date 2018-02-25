---
title: __inbyte | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __inbyte
- __inbyte_cpp
dev_langs:
- C++
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3acb6e5a5fc5f9f9a6808ae8b2047da32b1b2d4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
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
|`__inbyte`|x86、 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="remarks"></a>コメント  
 このルーチンは、組み込みとしてのみ使用できます。  
  
## <a name="see-also"></a>参照  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)