---
title: "ModuleBase クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::ModuleBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ModuleBase クラス"
ms.assetid: edce7591-6893-46f7-94a7-382827775548
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ModuleBase クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
class ModuleBase;  
```  
  
## <a name="remarks"></a>コメント  
 基本クラスを表す、 [モジュール](../windows/module-class.md) クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Modulebase::modulebase コンス トラクター](../windows/modulebase-modulebase-constructor.md)|モジュール クラスのインスタンスを初期化します。|  
|[ModuleBase:: ~ ModuleBase デストラクター](../windows/modulebase-tilde-modulebase-destructor.md)|モジュール クラスの現在のインスタンスの初期化を解除します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Modulebase::decrementobjectcount メソッド](../Topic/ModuleBase::DecrementObjectCount%20Method.md)|実装された場合、デクリメント オブジェクトの数によって追跡モジュール。|  
|[Modulebase::incrementobjectcount メソッド](../windows/modulebase-incrementobjectcount-method.md)|実装された場合、モジュールによって追跡されるオブジェクトの数をインクリメントします。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ModuleBase`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)