---
title: "marshal_context:: ~ marshal_context |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- marshal_context::~marshal_context
- msclr.interop.marshal_context.~marshal_context
- marshal_context.~marshal_context
- msclr::interop::marshal_context::~marshal_context
- ~marshal_context
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 42af11d58804a000e630d916cd5887c5005aa955
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::~marshal_context
`marshal_context` オブジェクトを破棄します。  
  
## <a name="syntax"></a>構文  
  
```  
~marshal_context();  
```  
  
## <a name="remarks"></a>コメント  
 一部のデータ変換では、マーシャ リング コンテキストが必要です。 参照してください[概要の C++ におけるマーシャ リング](../dotnet/overview-of-marshaling-in-cpp.md)コンテキストが必要にどの翻訳あり、マーシャ リング ファイル、アプリケーションに含まれるの詳細についてはします。  
  
 削除すると、`marshal_context`オブジェクトは、データをそのコンテキストで変換を無効になります。 後にデータを保持する場合、`marshal_context`オブジェクトが破棄されると、によって永続化される変数にデータを手動でコピーする必要があります。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー ファイル:** \<msclr\marshal.h >、 \<msclr\marshal_windows.h >、 \<msclr\marshal_cppstd.h >、または\<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>参照  
 [C++ におけるマーシャ リングの概要](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)   
 [marshal_context クラス](../dotnet/marshal-context-class.md)