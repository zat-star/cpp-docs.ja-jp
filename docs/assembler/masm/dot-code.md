---
title: ".コード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .CODE
dev_langs: C++
helpviewer_keywords: .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 150b5a0c26be3c3c4d0412157179ebfcbec128e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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