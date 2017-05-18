---
title: "コンテナー クラス::swap | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: f293f074f2b8e2334dc70fbebba8e6f4c17efecc
ms.openlocfilehash: 33ec601dcc8d32b85c2c38ed3fc5a07842a056fc
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="container-classswap"></a>コンテナー クラス::swap
> [!NOTE]
>  このトピックは、C++ 標準ライブラリで使用されるコンテナーの例 (実際には機能しない) として、Visual C++ ドキュメントに含まれています。 詳しくは、「[C++ 標準ライブラリのコンテナー](../standard-library/stl-containers.md)」をご覧ください。  
  
**\*this** とその引数の間で被制御シーケンスを交換します。  
  
## <a name="syntax"></a>構文  
  
```  
void swap(Container& right);
```  
  
## <a name="remarks"></a>コメント  
**\*this.get\_allocator ==** _right_**.get_allocator** の場合、一定時間で交換します。 それ以外の場合、2 つの被制御シーケンス内の要素数に比例した回数、要素の割り当てとコンストラクター呼び出しが実行されます。  
  
## <a name="see-also"></a>関連項目  
[サンプル コンテナー クラス](../standard-library/sample-container-class.md)

