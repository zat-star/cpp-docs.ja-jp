---
title: GetActivationFactory 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd269b8c2e1c671944305d385064d60e8bf9b8a1
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="getactivationfactory-function"></a>GetActivationFactory 関数
テンプレート パラメーターによって指定された型の対応するアクティベーション ファクトリを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 アクティベーション ファクトリの種類を指定するテンプレート パラメーター。  
  
 `activatableClassId`  
 アクティベーション ファクトリを作成できるクラスの名前。  
  
 `factory`  
 この操作の完了時、アクティベーション ファクトリの種類への参照を`T`です。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、この操作が失敗した理由を示す HRESULT エラーです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **Namespace:** windows::foundation  
  
## <a name="see-also"></a>関連項目  
 [Windows::Foundation 名前空間](../windows/windows-foundation-namespace.md)