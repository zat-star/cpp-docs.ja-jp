---
title: "Module::registerobjects メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::RegisterObjects
dev_langs: C++
helpviewer_keywords: RegisterObjects method
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5e73a59ff18c16a898ca1a9d7919615a2dec18bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="moduleregisterobjects-method"></a>Module::RegisterObjects メソッド
他のアプリケーションがそれらに接続できるように、COM または Windows ランタイム オブジェクトを登録します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `module`  
 COM または Windows ランタイムのオブジェクトの配列。  
  
 `serverName`  
 オブジェクトを作成したサーバーの名前です。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、原因を示す HRESULT 操作に失敗しました。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
## <a name="see-also"></a>参照
[Module クラス](../windows/module-class.md)