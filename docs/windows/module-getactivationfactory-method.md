---
title: "Module::GetActivationFactory メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::GetActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetActivationFactory メソッド"
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Module::GetActivationFactory メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

モジュールのアクティベーション ファクトリを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pActivatibleClassId`  
 ランタイム クラスの IID です。  
  
 `ppIFactory`  
 指定したランタイム クラスの IActivationFactory です。  
  
 `serverName`  
 現在のモジュール内のクラス ファクトリのサブセットの名前。 使用されるサーバー名を指定、 [ActivatableClassWithFactoryEx](../Topic/ActivatableClass%20Macros.md) マクロ、または指定 `nullptr` を既定のサーバー名を取得します。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKGetActivationFactory によってそれ以外の場合、HRESULT が返されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>「  
[モジュール クラス](../windows/module-class.md)
 [ActivatableClass マクロ](../Topic/ActivatableClass%20Macros.md)