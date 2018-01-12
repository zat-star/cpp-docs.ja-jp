---
title: "EXTERNDEF |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EXTERNDEF
dev_langs: C++
helpviewer_keywords: EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a06378b7cf1217c01f57d7994220bfe5dd585a66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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