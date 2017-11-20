---
title: "_com_error::Error |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::Error
- Error
dev_langs: C++
helpviewer_keywords: Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 010d1b2e10d1435855c35929516ff0e7f3fd8d4e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="comerrorerror"></a>_com_error::Error
**Microsoft 固有の仕様**  
  
 コンストラクターに渡された `HRESULT` を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
HRESULT Error( ) const throw( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 コンストラクターに渡された未処理の `HRESULT` 項目。  
  
## <a name="remarks"></a>コメント  
 `HRESULT` オブジェクト内のカプセル化された `_com_error` 項目を取得します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)