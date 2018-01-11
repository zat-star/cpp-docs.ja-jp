---
title: "Criticalsection::criticalsection コンス トラクター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs: C++
helpviewer_keywords: CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 532a7b2e046bbdb64db118741a939dadb049f081
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectioncriticalsection-constructor"></a>CriticalSection::CriticalSection コンストラクター
ミュー テックス オブジェクトに似ていますが、1 つのプロセスのスレッドのみで使用できる同期オブジェクトを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `spincount`  
 クリティカル セクション オブジェクト用のスピン カウントします。 既定値は 0 です。  
  
## <a name="remarks"></a>コメント  
 クリティカル セクションおよび spincounts の詳細については、次を参照してください。、 **InitializeCriticalSectionAndSpinCount**関数については、Windows API ドキュメントの [同期] セクションでします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [CriticalSection クラス](../windows/criticalsection-class.md)
