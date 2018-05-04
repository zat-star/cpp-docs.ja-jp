---
title: -DYNAMICBASE |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /dynamicbase
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d7a4cf7aa35d7ad6b41fc6d61f3f27662ae2c8d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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