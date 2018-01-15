---
title: "Module::module コンス トラクター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::Module
dev_langs: C++
helpviewer_keywords: Module, constructor
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 24e74bf30f932fa8029c64d27ce55dd2a75a99aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="modulemodule-constructor"></a>Module::Module コンストラクター
モジュール クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
Module();  
```  
  
## <a name="remarks"></a>コメント  
 このコンス トラクターが保護されているし、で呼び出すことはできません、`new`キーワード。 代わりに、いずれかを呼び出す[module::getmodule メソッド](../windows/module-getmodule-method.md)または[module::create メソッド](../windows/module-create-method.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>参照
 [Module クラス](../windows/module-class.md)