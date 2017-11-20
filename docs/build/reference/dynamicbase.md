---
title: "-DYNAMICBASE |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /dynamicbase
dev_langs: C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b5af34353db3c5b7cebaf02e8ce6b1bd9518cc8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="dynamicbase"></a>/DYNAMICBASE
ASLR (Address Space Layout Randomization) 機能を使用して、読み込み時に実行可能イメージをランダムにリベースできるかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
/DYNAMICBASE[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 既定では、リンカー設定、 **/DYNAMICBASE**オプション。  
  
 このオプションは、実行可能イメージのヘッダーを変更して、読み込み時に、ローダーがランダムにイメージをリベースできるかどうかを示します。  
  
 ASLR は、Windows Vista、Windows Server 2008、Windows 7、Windows 8、および Windows Server 2012 でサポートされています。  
  
## <a name="see-also"></a>関連項目  
 [EDITBIN オプション](../../build/reference/editbin-options.md)   
 [Windows ISV Software Security Defenses](http://msdn.microsoft.com/library/bb430720.aspx)