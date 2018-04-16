---
title: "uuid (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- uuid_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c999b429cb789167eeb754b6f11a8b3d90c28642
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2018
---
# <a name="uuid-c"></a>uuid (C++)
**Microsoft 固有の仕様**  
  
 コンパイラは、`uuid` 属性で宣言または定義された (完全な COM オブジェクト定義のみ) クラスまたは構造体に GUID をアタッチします。  
  
## <a name="syntax"></a>構文  
  
```  
  
__declspec( uuid("ComObjectGUID") ) declarator  
```  
  
## <a name="remarks"></a>コメント  
 `uuid` 属性は、引数として文字列を受け取ります。 この文字列が標準レジストリ形式の有無で GUID を名前、 **{}**区切り記号。 例:  
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 この属性は、再宣言で適用できます。 これにより、システム ヘッダーなどのインターフェイスの定義を指定する**IUnknown**、および他のヘッダーで再宣言 (など\<comdef.h >) GUID を提供します。  
  
 キーワード[_ _uuidof](../cpp/uuidof-operator.md) GUID が、ユーザー定義型にアタッチされている定数の取得に適用できます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [__declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)