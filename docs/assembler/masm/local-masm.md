---
title: "ローカル (MASM) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Local
dev_langs: C++
helpviewer_keywords: LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 45ee0a98d614ee10cb7393c0e616459526b37531
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="local-masm"></a>LOCAL (MASM)
マクロ、内の最初のディレクティブで**ローカル**マクロの各インスタンスに固有のラベルを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      LOCAL localname [[, localname]]...  
LOCAL label [[ [count ] ]] [[:type]] [[, label [[ [count] ]] [[type]]]]...  
```  
  
## <a name="remarks"></a>コメント  
 プロシージャ定義内で、次のディレクティブ (**PROC**)、**ローカル**プロシージャの実行中に存在しているスタック ベースの変数を作成します。 *ラベル*単純な変数またはを含む配列にすることがあります*カウント*要素。  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)