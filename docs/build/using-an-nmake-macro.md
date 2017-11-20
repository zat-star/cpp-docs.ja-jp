---
title: "NMAKE マクロの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9893e7ec1ba29b4b5ed2ccb569a135f44b2ed47f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="using-an-nmake-macro"></a>NMAKE マクロの使用
マクロを使用するのには、ドル記号 ($) を次のように続くかっこ内にその名前を囲みます。  
  
## <a name="syntax"></a>構文  
  
```  
$(macroname)  
```  
  
## <a name="remarks"></a>コメント  
 スペースは許可されません。 かっこは省略可能な場合は*macroname*は、1 つの文字です。 定義の文字列に $ が置き換えられます (*macroname*); 未定義マクロは、null 文字列に置換します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
 [マクロでの代入](../build/macro-substitution.md)  
  
## <a name="see-also"></a>関連項目  
 [マクロと NMAKE](../build/macros-and-nmake.md)