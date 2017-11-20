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
ms.openlocfilehash: 33d8d31a7f605fb22e3ca925d53b22b3034c0a7b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="modulemodule-constructor"></a>Module::Module コンストラクター
モジュール クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
Module();  
```  
  
## <a name="remarks"></a>コメント  
 このコンス トラクターが保護されているし、で呼び出すことはできません、`new`キーワード。 代わりに、いずれかを呼び出す[module::getmodule メソッド](../windows/module-getmodule-method.md)または[module::create メソッド](../windows/module-create-method.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)