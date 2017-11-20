---
title: "Interfacetraits::fillarraywithiid メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
dev_langs: C++
helpviewer_keywords: FillArrayWithIid method
ms.assetid: 73583177-adc9-4fcb-917d-fa7e6d07c990
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 014d47e650cf27f7e5a70ad63b0f6de21e5e5ccd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="interfacetraitsfillarraywithiid-method"></a>InterfaceTraits::FillArrayWithIid メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `index`  
 0 から始まるインデックス値を含むフィールドへのポインター。  
  
 `iids`  
 インターフェイスの Id の配列。  
  
## <a name="remarks"></a>コメント  
 インターフェイス ID を割り当てます`Base`インデックス引数で指定された配列の要素にします。  
  
 この API の名前とは対照的 1 つだけの配列要素が変更されました。全体の配列ではありません。  
  
 詳細については`Base`、パブリック Typedef セクションを参照して[InterfaceTraits 構造体](../windows/interfacetraits-structure.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [InterfaceTraits 構造体](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)