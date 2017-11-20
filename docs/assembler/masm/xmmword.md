---
title: "XMMWORD |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: XMMWORD
dev_langs: C++
helpviewer_keywords: XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 34bed9288320a5a8eadca88c67da72dd6ee2094d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="xmmword"></a>XMMWORD
MMX と SSE (XMM) の命令では、128 ビットのマルチ メディア オペランドに使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
XMMWORD  
```  
  
## <a name="remarks"></a>コメント  
 `XMMWORD`同じ型を表すために、 [_ _m128](../../cpp/m128.md)です。  
  
## <a name="example"></a>例  
  
```  
movdqa   xmm0, xmmword ptr [ebx]  
```