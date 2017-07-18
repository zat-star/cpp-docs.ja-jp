---
title: "ゼロ メモリの割り当て | Microsoft Docs"
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
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 76ee39b92d9ebd8ad75f70603e491b3b358c3bbe
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="allocating-zero-memory"></a>ゼロ メモリの割り当て
**ANSI 4.10.3** 要求されたサイズがゼロの場合の `calloc`、`malloc`、または `realloc` 関数の動作  
  
 `calloc`、`malloc`、および `realloc` 関数は、引数として 0 を受け入れます。 実際のメモリの割り当てはありませんが、有効なポインターが返され、メモリ ブロックは realloc によって後で変更できます。  
  
## <a name="see-also"></a>関連項目  
 [ライブラリ関数](../c-language/library-functions.md)
