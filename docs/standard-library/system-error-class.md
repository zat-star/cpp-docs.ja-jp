---
title: "system_error クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "system_error/std::system_error"
  - "std.system_error"
  - "std::system_error"
  - "system_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "system_error クラス"
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# system_error クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

低レベルのシステム エラーを報告するすべての例外の基本クラスを表します。  
  
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
  
## <a name="remarks"></a>解説  
 によって返される値 `what` クラスで [例外](../standard-library/exception-class1.md) から構築された `_Message` と格納されているオブジェクトの種類の [error_code](../standard-library/error-code-class.md) (どちらか `code` または `error_code(_Errval, _Errcat)`)。  
  
 メンバー関数は、 `code` の格納を返します。 [error_code](../standard-library/error-code-class.md) オブジェクトです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \< system_error >  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [\< system_error >](../standard-library/system-error.md)

