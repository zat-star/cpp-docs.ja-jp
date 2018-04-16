---
title: MMWORD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- MMWORD
dev_langs:
- C++
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0570a55dc11994e12acedb85d3ae8015abefb54c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="mmword"></a>MMWORD
MMX と SSE (XMM) の命令で 64 ビットのマルチ メディア オペランドに使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
MMWORD  
```  
  
## <a name="remarks"></a>コメント  
 `MMWORD` 型です。  MMWORD MASM に追加されている、前に、同等の機能を実現されてがでした。  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 両方の手順については、64 ビットのオペランドで作業中に`QWORD`は 64 ビット符号なし整数値の型と`MMWORD`は 64 ビットのマルチ メディア値の型です。  
  
 `MMWORD` 同じ型を表すために、 [_ _m64](../../cpp/m64.md)です。  
  
## <a name="example"></a>例  
  
```  
movq     mm0, mmword ptr [ebx]  
```