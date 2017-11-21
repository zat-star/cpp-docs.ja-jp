---
title: "Module::releasenotifier クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::ReleaseNotifier
dev_langs: C++
helpviewer_keywords: ReleaseNotifier class
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b48374182d9b39d43cbf0ec99cb51075867e914d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier クラス
モジュール内の最後のオブジェクトを解放すると、イベント ハンドラーを呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
class ReleaseNotifier;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Module::ReleaseNotifier::~ReleaseNotifier デストラクター](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|Module::releasenotifier クラスの現在のインスタンスの初期化を解除します。|  
|[Module::ReleaseNotifier::ReleaseNotifier コンストラクター](../windows/module-releasenotifier-releasenotifier-constructor.md)|Module::releasenotifier クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Module::ReleaseNotifier::Invoke メソッド](../windows/module-releasenotifier-invoke-method.md)|実装された場合、モジュール内の最後のオブジェクトが離されると、イベント ハンドラーを呼び出します。|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|パラメーターを持つオブジェクトを構築した場合は、現在の module::releasenotifier オブジェクトを削除`true`です。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)