---
title: "Hstring::hstring コンス トラクター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs: C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d13f532484cc071744b9b823546052d92c6f6b78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hstringhstring-constructor"></a>HString::HString コンストラクター
HString クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HString(HSTRING hstr = nullptr) throw();  
HString(HString&& other) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hstr`  
 HSTRING ハンドルの場合です。  
  
 `other`  
 既存の HString オブジェクト。  
  
## <a name="remarks"></a>コメント  
 最初のコンス トラクターは、空である新しい HString オブジェクトを初期化します。  
  
 2 番目のコンス トラクターは、既存の値に新しい HString オブジェクトを初期化します`other`パラメーターを破棄し、および、`other`パラメーター。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [HString クラス](../windows/hstring-class.md)