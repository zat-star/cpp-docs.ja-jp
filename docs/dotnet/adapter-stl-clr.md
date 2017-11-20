---
title: "アダプター (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: <cliext/adapter>
dev_langs: C++
helpviewer_keywords:
- <adapter> header [STL/CLR]
- adapter [STL/CLR]
- <cliext/adapter> header [STL/CLR]
ms.assetid: 71ce7e51-42b6-4f70-9595-303791a97677
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc5480896ed931fffdd4087eb5f39cfd8bbe67aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="adapter-stlclr"></a>adapter (STL/CLR)
STL/CLR ヘッダー `<cliext/adapter>` 2 つのテンプレート クラスを指定します (`collection_adapter`と`range_adapter`)、およびテンプレート関数は、`make_collection`です。  
  
## <a name="syntax"></a>構文  
  
```  
#include <cliext/adapter>  
```  
  
## <a name="remarks"></a>コメント  
  
|クラス|説明|  
|-----------|-----------------|  
|[collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)|範囲として基本クラス ライブラリ (BCL) コレクションをラップします。|  
|[range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)|BCL コレクションとして範囲をラップします。|  
  
|関数|説明|  
|--------------|-----------------|  
|[make_collection (STL/CLR)](../dotnet/make-collection-stl-clr.md)|反復子のペアを使用して範囲アダプターを作成します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アダプター/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)