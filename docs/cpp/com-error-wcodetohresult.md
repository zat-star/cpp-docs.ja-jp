---
title: "_com_error::WCodeToHRESULT |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::WCodeToHRESULT
dev_langs:
- C++
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: e5165f3bf0058d2c1f5ae4cb416fd6b26e0077d3
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT
**Microsoft 固有の仕様**  
  
 16 ビットをマップ`wCode`32 ビット`HRESULT`です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `wCode`  
 32 ビットの `wCode` にマップされる 16 ビットの `HRESULT`。  
  
## <a name="return-value"></a>戻り値  
 16 ビットの `HRESULT` からマップされた 32 ビットの `wCode`。  
  
## <a name="remarks"></a>コメント  
 参照してください、 [WCode](../cpp/com-error-wcode.md)メンバー関数。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error::wcode](../cpp/com-error-wcode.md)   
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error クラス](../cpp/com-error-class.md)
