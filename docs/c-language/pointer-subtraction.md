---
title: "ポインターの減算 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- pointer subtraction
ms.assetid: 4d515690-088a-43f6-bb8c-57b849f7ccf7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10d40cbac5e9320ee335fa4c8090aa11d5157ae3
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="pointer-subtraction"></a>ポインターの減算
**ANSI 3.3.6, 4.1.1** 同じ配列の要素への 2 つのポインター間の差を保持するために必要な整数型、**ptrdiff_t**  
  
 `ptrdiff_t` は、32 ビット x86 プラットフォームでは `int` です。 64 ビット プラットフォームでは、`ptrdiff_t` typedef は `__int64` です。
  
## <a name="see-also"></a>参照  
 [配列とポインター](../c-language/arrays-and-pointers.md)
