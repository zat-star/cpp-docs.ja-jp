---
title: "ファイル位置エラー | Microsoft Docs"
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
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: ebbb6ab903db73fce84059af567dd5e80dfb3afb
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="file-position-errors"></a>ファイル位置エラー
**ANSI 4.9.9.1, 4.9.9.4** 失敗時に `fgetpos` または `ftell` 関数によって `errno` マクロが設定された値  
  
 `fgetpos` または `ftell` が失敗すると、`errno` は、位置が無効である場合はマニフェスト定数 `EINVAL` に設定され、ファイル番号が無効である場合は EBADF に設定されます。 これらの定数は、ERRNO.H で定義されています。  
  
## <a name="see-also"></a>関連項目  
 [ライブラリ関数](../c-language/library-functions.md)
