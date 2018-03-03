---
title: "ワイド文字 | Microsoft Docs"
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
- wide characters
ms.assetid: 165c4a12-8ab9-45fb-9964-c55e9956194c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab885d5d807fe81b3058d533a70cdbaa9e3e523a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="wide-characters"></a>Wide Characters (ワイド文字)
**ANSI 3.1.3.4** 複数の文字を含む整数文字定数、または、複数のマルチバイト文字を含むワイド文字定数の値  
  
 通常の文字定数 'ab' は、整数値 (int)0x6162 を持ちます。 1 バイトを超える場合は、以前に読み取られたバイトが **CHAR_BIT** の値だけ左にシフトされ、次のバイトがビットごとの OR 演算子を使用して **CHAR_BIT** 分の下位ビットと比較されます。 マルチバイト文字定数のバイト数は sizeof (int) を超えることはできません。これは 32 ビット対象のコードでは 4 です。  
  
 マルチバイト文字定数は、上記のように読み取られ、これが `mbtowc` ランタイム関数を使用してワイド文字定数に変換されます。 結果が有効なワイド文字定数でない場合は、エラーが発行されます。 いずれの場合も、`mbtowc` 関数でチェックするバイト数は `MB_CUR_MAX` の値に制限されます。  
  
## <a name="see-also"></a>参照  
 [文字](../c-language/characters.md)