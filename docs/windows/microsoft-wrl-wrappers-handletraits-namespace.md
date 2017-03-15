---
title: "Microsoft::WRL::Wrappers::HandleTraits 名前空間 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HandleTraits 名前空間"
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Microsoft::WRL::Wrappers::HandleTraits 名前空間
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

一般的なハンドル ベースのリソースの種類の特徴について説明します。  
  
## <a name="syntax"></a>構文  
  
```  
namespace Microsoft::WRL::Wrappers::HandleTraits;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="structures"></a>構造体  
  
|名前|説明|  
|----------|-----------------|  
|[CriticalSectionTraits 構造体](../windows/criticalsectiontraits-structure.md)|専門としています、 `CriticalSection` 無効なクリティカル セクション、または、クリティカル セクションを解放する関数をサポートするオブジェクト。|  
|[EventTraits 構造体](../windows/eventtraits-structure.md)|特性を定義、 `Event` クラスのハンドル。|  
|[FileHandleTraits 構造体](../windows/filehandletraits-structure.md)|ファイル ハンドルの特性を定義します。|  
|[HANDLENullTraits 構造体](../windows/handlenulltraits-structure.md)|初期化されていないハンドルの一般的な特徴を定義します。|  
|[HANDLETraits 構造体](../windows/handletraits-structure.md)|ハンドルの一般的な特徴を定義します。|  
|[MutexTraits 構造体](../windows/mutextraits-structure.md)|一般的な特性を定義、 [ミュー テックス](Mutex%20Class1.md) クラスです。|  
|[SemaphoreTraits 構造体](../Topic/SemaphoreTraits%20Structure.md)|セマフォ オブジェクトの共通の特徴を定義します。|  
|[SRWLockExclusiveTraits 構造体](../windows/srwlockexclusivetraits-structure.md)|一般的な特性を記述、 `SRWLock` 排他ロックのモードでのクラスです。|  
|[SRWLockSharedTraits 構造体](../windows/srwlocksharedtraits-structure.md)|一般的な特性を記述、 `SRWLock` 共有ロックのモードでのクラスです。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers 名前空間](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)