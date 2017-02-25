---
title: "Module::RegisterCOMObject メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::RegisterCOMObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterCOMObject メソッド"
ms.assetid: 59f223dc-03c6-429d-95da-b74b3f73b702
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Module::RegisterCOMObject メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

他のアプリケーションがそれらに接続できるように、1 つまたは複数の COM オブジェクトを登録します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW virtual HRESULT RegisterCOMObject(  
   const wchar_t* serverName,  
   IID* clsids,  
   IClassFactory** factories,  
   DWORD* cookies,  
   unsigned int count);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `serverName`  
 サーバーの完全修飾名。  
  
 `clsids`  
 登録する Clsid の配列。  
  
 `factories`  
 可用性が公開されているクラス オブジェクトの IUnknown インターフェイスの配列。  
  
 `cookies`  
 操作が完了したらは、登録され、そのオブジェクト クラスを識別する値へのポインターの配列。 これらの値は使用後で登録を取り消します。  
  
 `count`  
 登録する Clsid の数。  
  
## <a name="return-value"></a>戻り値  
 S_OK 場合 successfu です。それ以外の場合、HRESULT の理由を示す CO_E_OBJISREG など、操作に失敗しました。  
  
## <a name="remarks"></a>コメント  
 COM オブジェクトは、CLSCTX 列挙体の CLSCTX_LOCAL_SERVER 列挙子が登録されます。  
  
 登録済みのオブジェクトへの接続の種類が、現在の組み合わせで指定された `comflag` テンプレート パラメーターと REGCLS 列挙体の REGCLS_SUSPENDED 列挙子。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>「
 [モジュール クラス](../windows/module-class.md)