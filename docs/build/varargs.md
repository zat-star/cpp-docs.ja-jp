---
title: "Varargs |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3d22a5c3f20480d1e904ec8e087114385ba7ee9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="varargs"></a>vararg
パラメーターが varargs (たとえば、省略記号引数) を使用して指定された場合、基本的には、通常のパラメーターを渡すでは以降の 5 番目の引数に書き込むときに含めが適用されます。 再度、アドレスを与えるダンプ引数に、呼び出し先の責任です。 浮動小数点値の場合にのみ、整数と浮動小数点レジスタの両方値が含まれます、float 場合に、呼び出し先は、整数レジスタに値が必要です。  
  
## <a name="see-also"></a>参照  
 [呼び出し規則](../build/calling-convention.md)