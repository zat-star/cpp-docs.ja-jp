---
title: "Microsoft::WRL::Wrappers::HandleTraits Namespace |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
dev_langs:
- C++
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aec9ff1b4294257f692d76a96960820379116b0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits 名前空間
一般的なハンドル ベースのリソースの種類の特性について説明します。  
  
## <a name="syntax"></a>構文  
  
```  
namespace Microsoft::WRL::Wrappers::HandleTraits;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="structures"></a>構造体  
  
|名前|説明|  
|----------|-----------------|  
|[CriticalSectionTraits 構造体](../windows/criticalsectiontraits-structure.md)|特殊化した、`CriticalSection`無効な重要なセクションまたは重要なセクションを解除する機能をサポートするオブジェクト。|  
|[EventTraits 構造体](../windows/eventtraits-structure.md)|特性を定義、`Event`クラスのハンドル。|  
|[FileHandleTraits 構造体](../windows/filehandletraits-structure.md)|ファイル ハンドルの特性を定義します。|  
|[HANDLENullTraits 構造体](../windows/handlenulltraits-structure.md)|初期化されていないハンドルの共通の特性を定義します。|  
|[HANDLETraits 構造体](../windows/handletraits-structure.md)|ハンドルの共通の特性を定義します。|  
|[MutexTraits 構造体](../windows/mutextraits-structure.md)|一般的な特性を定義、[ミュー テックス](../windows/mutex-class1.md)クラスです。|  
|[SemaphoreTraits 構造体](../windows/semaphoretraits-structure.md)|セマフォ オブジェクトの共通の特性を定義します。|  
|[SRWLockExclusiveTraits 構造体](../windows/srwlockexclusivetraits-structure.md)|一般的な特性を記述、`SRWLock`排他ロックのモードでのクラスです。|  
|[SRWLockSharedTraits 構造体](../windows/srwlocksharedtraits-structure.md)|一般的な特性を記述、`SRWLock`共有ロック モードでのクラスです。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)