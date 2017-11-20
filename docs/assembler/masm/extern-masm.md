---
title: "EXTERN (MASM) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: extern
dev_langs: C++
helpviewer_keywords: EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 418ca4e5844250e2ebd34c799bc6001cf6f2f61e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="extern-masm"></a>EXTERN (MASM)
1 つまたは複数の外部変数、ラベル、または記号と呼ばれる定義*名前*型を持つ`type`します。  
  
## <a name="syntax"></a>構文  
  
```  
  
   EXTERN [[langtype]] name [[(altid)]] :  
type [[, [[langtype]] name [[(altid)]] :type]]...  
```  
  
## <a name="remarks"></a>コメント  
 `type`できます[ABS](../../assembler/masm/operator-abs.md)、どの imports*名前*定数として。 同じ[EXTRN](../../assembler/masm/extrn.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)