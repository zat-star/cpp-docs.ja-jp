---
title: "SRWLock クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::SRWLock
dev_langs: C++
helpviewer_keywords: SRWLock class
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1325a089739b3820009aa239f56805264dbb6b83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="srwlock-class"></a>SRWLock クラス
スリム リーダー/ライター ロックに相当します。  
  
## <a name="syntax"></a>構文  
  
```  
class SRWLock;  
```  
  
## <a name="remarks"></a>コメント  
 スリム リーダー/ライター ロックは、オブジェクトまたはリソースへのスレッド間でのアクセスを同期するために使用されます。 詳細については、次を参照してください。[同期関数](http://msdn.microsoft.com/en-us/9b6359c2-0113-49b6-83d0-316ad95aba1b)です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|||  
|-|-|  
|**SyncLockExclusive**|排他モードで取得した SRWLock オブジェクトのシノニムです。|  
|**SyncLockShared**|共有モードで取得した SRWLock オブジェクトのシノニムです。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SRWLock::SRWLock コンストラクター](../windows/srwlock-srwlock-constructor.md)|SRWLock クラスの新しいインスタンスを初期化します。|  
|[SRWLock::~SRWLock デストラクター](../windows/srwlock-tilde-srwlock-destructor.md)|SRWLock クラスのインスタンスの初期化を解除します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SRWLock::LockExclusive メソッド](../windows/srwlock-lockexclusive-method.md)|排他モードで SRWLock オブジェクトを取得します。|  
|[SRWLock::LockShared メソッド](../windows/srwlock-lockshared-method.md)|共有モードで SRWLock オブジェクトを取得します。|  
|[SRWLock::TryLockExclusive メソッド](../windows/srwlock-trylockexclusive-method.md)|現在または指定した SRWLock オブジェクトの排他モードで SRWLock オブジェクトを取得しようとしています。|  
|[SRWLock::TryLockShared メソッド](../windows/srwlock-trylockshared-method.md)|現在または指定した SRWLock オブジェクトの共有モードで SRWLock オブジェクトを取得しようとしています。|  
  
### <a name="protected-data-member"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[SRWLock::SRWLock_ データ メンバー](../windows/srwlock-srwlock-data-member.md)|現在の SRWLock オブジェクトの基になるロック変数が含まれています。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SRWLock`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)