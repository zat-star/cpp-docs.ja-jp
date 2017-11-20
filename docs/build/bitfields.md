---
title: "ビット フィールド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: bitfields
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ebdfd892b164d10fbed46a481184c23113af4bc5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="bitfields"></a>ビット フィールド
構造体のビット フィールドは 64 ビットに制限されており、型は int、unsigned int 型、int64、または符号なしの int64 の署名します。 型の境界を越えることがビット フィールドでは、[次へ] の型のアラインメントをビット フィールドを配置するをスキップします。 たとえば、整数のビット フィールドを超えることは 32 ビットの境界。  
  
## <a name="see-also"></a>関連項目  
 [型とストレージ](../build/types-and-storage.md)