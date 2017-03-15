---
title: "Module::UnregisterWinRTObject メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::UnregisterWinRTObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnregisterWinRTObject メソッド"
ms.assetid: 32334aa7-2293-40d2-9a89-4b02e2e31f3c
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Module::UnregisterWinRTObject メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

1 つまたは複数の登録を解除 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] オブジェクトを他のアプリケーションがそれらに接続できないようにします。  
  
## <a name="syntax"></a>構文  
  
```  
virtual HRESULT UnregisterWinRTObject(  
   unsigned int,  
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cookie`  
 登録は無効にする、クラス オブジェクトを識別する値へのポインター。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>「
 [モジュール クラス](../windows/module-class.md)