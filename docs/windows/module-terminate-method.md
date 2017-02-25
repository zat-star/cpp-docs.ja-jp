---
title: "Module::Terminate メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::Terminate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Terminate メソッド"
ms.assetid: cf358117-45dc-43c7-ac1e-1e1eedc59e41
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Module::Terminate メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

シャット ダウンするモジュールによってインスタンス化されたすべてのファクトリをさせます。  
  
## <a name="syntax"></a>構文  
  
```  
void Terminate();  
```  
  
## <a name="remarks"></a>コメント  
 キャッシュ内のファクトリを解放します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>「
 [モジュール クラス](../windows/module-class.md)