---
title: "is_error_code_enum クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::is_error_code_enum
- is_error_code_enum
dev_langs:
- C++
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
caps.latest.revision: 15
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 65c818260a4da28c3134e7fb9e124993b0200b74
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

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




