---
title: EXTERNDEF | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- EXTERNDEF
dev_langs:
- C++
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a463f4f74f380c6d927419eb498ccd868587ac6d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="externdef"></a>EXTERNDEF
1 つまたは複数の外部変数、ラベル、または記号と呼ばれる定義*名前*型を持つ`type`します。  
  
## <a name="syntax"></a>構文  
  
```  
  
EXTERNDEF [[langtype]] name:type [[, [[langtype]] name:type]]...  
```  
  
## <a name="remarks"></a>コメント  
 場合*名前*が定義されているモジュールでは、そのとして扱われます[パブリック](../../assembler/masm/public-masm.md)です。 場合*名前*が参照されているモジュールでは、そのとして扱われます[EXTERN](../../assembler/masm/extern-masm.md)です。 場合*名前*が参照されないと、これは無視されます。 `type`できます[ABS](../../assembler/masm/operator-abs.md)、どの imports*名前*定数として。 通常使用されるインクルード ファイルに含めます。  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)