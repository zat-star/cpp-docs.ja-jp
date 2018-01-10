---
title: "_com_error::HRESULTToWCode |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::HRESULTToWCode
dev_langs: C++
helpviewer_keywords: HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 14c4cdf85e67bdb0acd8dbadd178e3fbd2dbaf54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [_com_error::wcode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error クラス](../cpp/com-error-class.md)