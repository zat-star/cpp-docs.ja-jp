---
title: "ビット フィールド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- bitfields
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 231d84e5d99cd9e6c1238ae12c143636f62ce80d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bitfields"></a>ビット フィールド
構造体のビット フィールドは 64 ビットに制限されており、型は int、unsigned int 型、int64、または符号なしの int64 の署名します。 型の境界を越えることがビット フィールドでは、[次へ] の型のアラインメントをビット フィールドを配置するをスキップします。 たとえば、整数のビット フィールドを超えることは 32 ビットの境界。  
  
## <a name="see-also"></a>参照  
 [型とストレージ](../build/types-and-storage.md)