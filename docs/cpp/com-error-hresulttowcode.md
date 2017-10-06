---
title: "_com_error::HRESULTToWCode |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::HRESULTToWCode
dev_langs:
- C++
helpviewer_keywords:
- HRESULTToWCode method
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
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
ms.openlocfilehash: 296c6f43c1bc840ae13bdf4ad355d7f41e2cc3fd
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Microsoft 固有の仕様**  
  
 32 ビットの `HRESULT` を 16 ビットの `wCode` にマップします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hr`  
 32 ビット`HRESULT`16 ビットにマップする`wCode`です。  
  
## <a name="return-value"></a>戻り値  
 16 ビット`wCode`32 ビットからマップされた`HRESULT`です。  
  
## <a name="remarks"></a>コメント  
 参照してください[_com_error::wcode](../cpp/com-error-wcode.md)詳細についてはします。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error::wcode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error クラス](../cpp/com-error-class.md)
