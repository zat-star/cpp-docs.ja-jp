---
title: Comptr::as メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::As
dev_langs:
- C++
helpviewer_keywords:
- As method
ms.assetid: 2ad6c262-9bdb-4c59-a330-1af8bcd445cc
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8f3602e8be11fa1569117968848e60bd86f59acd
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="comptras-method"></a>ComPtr::As メソッド
指定されたテンプレート パラメーターで識別されるインターフェイスを表す ComPtr オブジェクトを返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
template<typename U>  
HRESULT As(  
   _Out_ ComPtr<U>* p  
) const;  
  
template<typename U>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> p  
) const;  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `U`  
 パラメーターによって表されるインターフェイス`p`です。  
  
 `p`  
 パラメーターで指定されたインターフェイスを表す ComPtr オブジェクト`U`です。 パラメーター`p`現在の ComPtr オブジェクトを参照する必要があります。  
  
## <a name="remarks"></a>コメント  
 最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレートは、 [auto](../cpp/auto-cpp.md) 型推論キーワードなどの C++ 言語の機能をサポートしている内部ヘルパーの特殊化です。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)