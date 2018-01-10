---
title: "Hstringreference::hstringreference コンス トラクター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
dev_langs: C++
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 398ea9403f784c30f8e015101c25b071f1d6fb29
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hstringreferencehstringreference-constructor"></a>HStringReference::HStringReference コンストラクター
HStringReference クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest],   
                 unsigned int len) throw();  
  
HStringReference(HStringReference&& other) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `sizeDest`  
 コピー先の HStringReference バッファーのサイズを指定するテンプレート パラメーター。  
  
 `str`  
 ワイド文字の文字列への参照。  
  
 `len`  
 最大長、`str`この操作で使用するパラメーター バッファーです。 場合、`len`パラメーターが指定されていない全体`str`パラメーターを使用します。 場合`len`がより大きい`sizeDest`、`len`に設定されている`sizeDest`-1 です。  
  
 `other`  
 別の HStringReference オブジェクトです。  
  
## <a name="remarks"></a>コメント  
 最初のコンス トラクターがパラメーターとしてのサイズを同じ新規の HStringReference オブジェクトを初期化します`str`です。  
  
 2 番目のコンス トラクター初期化新しい HStringReference オブジェクトをパラメーターでサイズ specifeid`len`です。  
  
 3 番目コンス トラクターは、新しい HStringReference オブジェクトの値を`other`パラメーターを破棄し、および、`other`パラメーター。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [HStringReference クラス](../windows/hstringreference-class.md)