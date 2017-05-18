---
title: "system_error クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::system_error
- system_error
dev_langs:
- C++
helpviewer_keywords:
- system_error class
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: cec13ab1b6358ffeb9c8df31154f5b706c266c5b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="systemerror-class"></a>system_error クラス
低レベル システムエラーをレポートするためにスローされるすべての例外のための基底クラスを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class system_error : public runtime_error {  
public:  
    explicit system_error(error_code _Errcode,
    const string& _Message = "");

    system_error(error_code _Errcode,
    const char *_Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const string& _Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const char *_Message);
const error_code& code() const throw();
const error_code& code() const throw();

 };  
```  
  
## <a name="remarks"></a>コメント  
 クラス [exception](../standard-library/exception-class.md) で `what` によって返される値は、`_Message` および型 [error_code](../standard-library/error-code-class.md) (`code` または `error_code(_Errval, _Errcat)` のいずれか) の格納されているオブジェクトから構築されます。  
  
 メンバー関数 `code` は、格納されている [error_code](../standard-library/error-code-class.md) オブジェクトを返します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<system_error>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<system_error>](../standard-library/system-error.md)


