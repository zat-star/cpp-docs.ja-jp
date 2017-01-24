---
title: "Module::GetClassObject メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::GetClassObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetClassObject メソッド"
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::GetClassObject メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス ファクトリのキャッシュを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
 HRESULT GetClassObject(  
   REFCLSID clsid,  
   REFIID riid,  
   _Deref_out_ void **ppv,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `clsid`  
 クラスの id。  
  
 `riid`  
 要求するインターフェイス ID です。  
  
 `ppv`  
 返されるオブジェクトへのポインター。  
  
 `serverName`  
 いずれかで指定されているサーバー名、 `ActivatableClassWithFactory`, 、`ActivatableClassWithFactoryEx`, 、または `ActivatableClass` マクロ; または `nullptr` を既定のサーバー名を取得します。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="remarks"></a>コメント  
 このメソッドをいない COM、に対してのみ使用、 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]です。 このメソッドは、IClassFactory メソッドのみを公開します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [モジュール クラス](../windows/module-class.md)