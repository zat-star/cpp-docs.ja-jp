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
ms.openlocfilehash: 4a884f4d3d1f754f12a23d6e24a6c1b533104e89
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)   
 [.DATA](../../assembler/masm/dot-data.md)