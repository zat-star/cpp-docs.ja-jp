---
title: "Module::UnregisterObjects メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::UnregisterObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnregisterObjects メソッド"
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Module::UnregisterObjects メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

その他のアプリケーションがそれらに接続できないように、指定したモジュール内のオブジェクトを登録解除します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT UnregisterObjects(  
   ModuleBase* module,  
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `module`  
 モジュールへのポインター。  
  
 `serverName`  
 この操作によって影響を受けるオブジェクトのサブセットを指定する修飾名。  
  
## <a name="return-value"></a>戻り値  
 この操作が成功した場合は S_OKそれ以外の場合、エラーの理由を示す hresult 値操作に失敗しました。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>「
 [モジュール クラス](../windows/module-class.md)