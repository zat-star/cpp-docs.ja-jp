---
title: "is_error_code_enum クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: system_error/std::is_error_code_enum
dev_langs: C++
helpviewer_keywords: is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fdaddd95ac6abf6355e93db28f1770b93d7725d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="iserrorcodeenum-class"></a>is_error_code_enum クラス
[error_code](../standard-library/error-code-class.md) 列挙型をテストする型述語を表します。  
  
## <a name="syntax"></a>構文  
  
```
template <_Enum>
class is_error_code_enum;
```  
  
## <a name="remarks"></a>コメント  
 型 `_Enum` が型 `error_code` のオブジェクトを格納するのに適した列挙型の値である場合、この[型述語](../standard-library/type-traits.md)のインスタンスは true を保持します。  
  
 ユーザー定義型のこの型に特殊化を追加できます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<system_error>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)   
 [<system_error>](../standard-library/system-error.md)



