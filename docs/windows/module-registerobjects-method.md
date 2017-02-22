---
title: "Module::RegisterObjects メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::RegisterObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterObjects メソッド"
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Module::RegisterObjects メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM に登録または [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] オブジェクトを他のアプリケーションがそれらに接続できるようにします。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `module`  
 COM の配列または [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] オブジェクトです。  
  
 `serverName`  
 オブジェクトを作成したサーバーの名前です。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合、理由を示す HRESULT 操作に失敗しました。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
## <a name="see-also"></a>「
[モジュール クラス](../windows/module-class.md)