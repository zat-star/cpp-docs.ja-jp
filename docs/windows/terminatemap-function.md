---
title: "TerminateMap 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::TerminateMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TerminateMap 関数"
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# TerminateMap 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
inline bool TerminateMap(  
   _In_ ModuleBase *module,   
   _In_opt_z_ const wchar_t *serverName,   
    bool forceTerminate) throw()  
```  
  
## <a name="parameters"></a>パラメーター  
 `module`  
 A [モジュール](../windows/module-class.md)します。  
  
 `serverName`  
 パラメーターで指定されたモジュールのクラス ファクトリのサブセットの名前 `module`します。  
  
 `forceTerminate`  
 `true` 関係なく、ファクトリはアクティブである、クラスを終了するには `false` に、ファクトリがアクティブである場合、クラス ファクトリを終了しません。  
  
## <a name="return-value"></a>戻り値  
 `true` 場合は、すべてのクラス ファクトリが終了しました。それ以外の場合、 `false`です。  
  
## <a name="remarks"></a>コメント  
 指定したモジュール内のクラス ファクトリを終了します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)