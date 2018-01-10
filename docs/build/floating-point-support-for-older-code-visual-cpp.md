---
title: "古いコード (Visual C) の浮動小数点サポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 130b6efb1c05775cd7859144d91a30051fb4ca53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="floating-point-support-for-older-code-visual-c"></a>旧形式のコードのための浮動小数点サポート (Visual C++)
MMX および浮動小数点スタック レジスタ (MM0-MM7/st0 を割り当てます-ST7) は、コンテキストの切り替えの間で保持されます。  これらのレジスタの明示的な呼び出し規則はありません。  これらのレジスタの使用は、カーネル モード コードで禁じられています。  
  
## <a name="see-also"></a>参照  
 [呼び出し規則](../build/calling-convention.md)