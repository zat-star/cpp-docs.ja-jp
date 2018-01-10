---
title: "char 型 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- type char
- unsigned char keyword [C]
- char keyword [C]
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9e3df3b4fd3e2763ef1704133cb111ee8ac067e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="type-char"></a>char 型
`char` 型は、表現できる文字セットのメンバーの整数値を格納するために使用されます。 この整数値は、特定の文字に対応する ASCII コードです。  
  
 **Microsoft 固有の仕様**  
  
 `unsigned char` 型の文字値の範囲は、16 進数で 0 から 0xFF までです。 **signed char** には 0x80 から 0x7F までの範囲があります。 これらの範囲は、0 から 255 の 10 進数と -128 から +127 の 10 進数にそれぞれ変換されます。 /J コンパイラ オプションは、既定値を **signed** から `unsigned` に変更します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [基本型の格納](../c-language/storage-of-basic-types.md)