---
title: "Module::RegisterWinRTObject メソッド | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::RegisterWinRTObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterWinRTObject メソッド"
ms.assetid: a2782c9c-b9c5-4e4b-9c8d-ef513aea20c5
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::RegisterWinRTObject メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

1 つまたは複数のレジスタ [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] オブジェクトを他のアプリケーションがそれらに接続できるようにします。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT RegisterWinRTObject(const wchar_t* serverName,  
   wchar_t** activatableClassIds,  
   WINRT_REGISTRATION_COOKIE* cookie,  
   unsigned int count)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `serverName`  
 この操作によって影響を受けるオブジェクトのサブセットを指定する名前です。  
  
 `activatableClassIds`  
 登録のアクティブ化可能な Clsid の配列。  
  
 `cookie`  
 登録済みのクラス オブジェクトを識別する値。 この値は、登録を取り消す後で使用されます。  
  
 `count`  
 登録するオブジェクトの数。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合、エラーの hresult 値などの理由を示す CO_E_OBJISREG 操作に失敗しました。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>「
 [モジュール クラス](../windows/module-class.md)