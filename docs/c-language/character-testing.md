---
title: "文字テスト | Microsoft Docs"
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
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: ca3c90169a3dab061a1e50e838b3432deec77b0c
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="character-testing"></a>文字テスト
**ANSI 4.3.1** `isalnum`、`isalpha`、`iscntrl`、`islower`、`isprint`、`isupper` 関数がテストする文字セット  
  
 次の一覧は、Microsoft C コンパイラによって実装された、これらの関数について説明します。  
  
|関数|テスト対象|  
|--------------|---------------|  
|`isalnum`|文字 0 - 9、A - Z、a - z、ASCII 48 - 57、65 - 90、97 - 122|  
|`isalpha`|文字 A - Z、a - z、ASCII 65 - 90、97 - 122|  
|`iscntrl`|ASCII 0 - 31、127|  
|`islower`|文字 a - z、ASCII 97 - 122|  
|`isprint`|文字 A - Z、a - z、0 - 9、句読点、スペース、ASCII 32 - 126|  
|`isupper`|文字 A - Z、ASCII 65 - 90|  
  
## <a name="see-also"></a>関連項目  
 [ライブラリ関数](../c-language/library-functions.md)
