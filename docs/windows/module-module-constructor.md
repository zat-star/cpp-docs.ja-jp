---
title: "Module::Module コンストラクター | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::Module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Module、コンストラクター"
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::Module コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

モジュール クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
Module();  
```  
  
## <a name="remarks"></a>コメント  
 このコンス トラクターが保護されておりを呼び出すことができない、 `new` キーワードです。 代わりに、いずれかを呼び出す [module::getmodule メソッド](../Topic/Module::GetModule%20Method.md) または [module::create メソッド](../windows/module-create-method.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [モジュール クラス](../windows/module-class.md)