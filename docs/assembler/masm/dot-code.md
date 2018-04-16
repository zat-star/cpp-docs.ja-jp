---
title: .CODE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .CODE
dev_langs:
- C++
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: de0a9b8930c04929b05b02931a1f796d28a78099
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="code"></a>.CODE
使用すると[です。モデル](../../assembler/masm/dot-model.md)、コード セグメントの開始を示します。  
  
## <a name="syntax"></a>構文  
  
```  
.CODE [[name]]  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`name`|コード セグメントの名前を指定する省略可能なパラメーターです。 既定の名前は非常に小さく、small、コンパクト、およびフラット _TEXT[モデル](../../assembler/masm/dot-model.md)です。 既定の名前は*modulename*_TEXT その他のモデル。|  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)   
 [.DATA](../../assembler/masm/dot-data.md)