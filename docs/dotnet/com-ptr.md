---
title: :ptr |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- ptr
dev_langs:
- C++
helpviewer_keywords:
- com::ptr
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 91c50379ae6514aa482cf4ee33eb7ff83fccc7b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptr"></a>com::ptr
CLR クラスのメンバーとして使用できる COM オブジェクトのラッパーです。 ラッパーは、またそのデストラクターが呼び出されたときに、オブジェクトに所有されている参照を解放し、COM オブジェクトの有効期間の管理を自動化します。 に似て[CComPtr クラス](../atl/reference/ccomptr-class.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
#include <msclr\com\ptr.h>  
```  
  
## <a name="remarks"></a>コメント  
 [:ptr クラス](../dotnet/com-ptr-class.md)で定義された、 \<msclr\com\ptr.h > ファイル。  
  
## <a name="see-also"></a>参照  
 [C++ のサポート ライブラリ](../dotnet/cpp-support-library.md)