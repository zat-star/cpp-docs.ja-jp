---
title: "_com_error::ErrorInfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::ErrorInfo
dev_langs: C++
helpviewer_keywords: ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 642078d84f72a553e9b2407b279265a3a7e77522
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo
**Microsoft 固有の仕様**  
  
 取得、 **IErrorInfo**オブジェクト コンス トラクターに渡されます。  
  
## <a name="syntax"></a>構文  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 Raw **IErrorInfo**項目が、コンス トラクターに渡されます。  
  
## <a name="remarks"></a>コメント  
 カプセル化された取得**IErrorInfo**内の項目、`_com_error`オブジェクト、または**NULL**いない場合**IErrorInfo**項目が記録されます。 呼び出し元が呼び出す必要があります**リリース**完了すると、返されたオブジェクトで使用します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_com_error クラス](../cpp/com-error-class.md)