---
title: "推論による依存ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 410e52dd9ee9605f6e29b81491bda0f4883e1cf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="inferred-dependents"></a>推論による依存ファイル
推論による依存ファイルでは、推論規則からは派生し、明示的な依存オブジェクトの前に評価されます。 推論による依存ファイルがターゲットと比べて古い場合は、(nmake の) は、依存関係のコマンド ブロックを呼び出します。 推論による依存ファイルが存在しないか、独自の依存オブジェクトに対して最新ではないが場合、(nmake の) は、推論による依存ファイルを最初に更新されます。 推論による依存ファイルの詳細については、次を参照してください。[推論規則](../build/inference-rules.md)です。  
  
## <a name="see-also"></a>参照  
 [依存](../build/dependents.md)