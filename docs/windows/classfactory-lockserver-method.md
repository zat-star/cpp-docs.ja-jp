---
title: "ClassFactory::LockServer メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ClassFactory::LockServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LockServer メソッド"
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ClassFactory::LockServer メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在の ClassFactory オブジェクトによって追跡されているオブジェクトの基になる数ずつインクリメントまたはデクリメントします。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fLock`  
 `true` 追跡対象オブジェクトの数をインクリメントします。 `false` 追跡対象オブジェクトの数をデクリメントします。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OKそれ以外の場合、E_FAIL します。  
  
## <a name="remarks"></a>コメント  
 ClassFactory の追跡の基になるインスタンス内のオブジェクト、 [モジュール](../windows/module-class.md) クラスです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ClassFactory クラス](../windows/classfactory-class.md)