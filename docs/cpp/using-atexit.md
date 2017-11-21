---
title: "Atexit の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: atexit
dev_langs: C++
helpviewer_keywords: atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 271dee456d47f9ef6286b4a9543583145f69bc41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="using-atexit"></a>atexit の使用
[Atexit](../c-runtime-library/reference/atexit.md)関数の場合、プログラムが終了する前に実行される終了処理関数を指定することができます。 `atexit` を呼び出す前に初期化されたグローバルな静的オブジェクトは、終了処理関数を実行するまでは破棄されません。  
  
## <a name="see-also"></a>関連項目  
 [終了に関するその他の考慮事項](../cpp/additional-termination-considerations.md)