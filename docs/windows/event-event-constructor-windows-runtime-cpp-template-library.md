---
title: "Event::event コンス トラクター (Windows ランタイム C++ テンプレート ライブラリ) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Event::Event
dev_langs: C++
ms.assetid: 21495297-9612-4095-9256-16e168cc0021
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63ca4f15dbbdd7f2423b34c0b7313a05976bcf77
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="eventevent-constructor-windows-runtime-c-template-library"></a>Event::Event コンストラクター (Windows ランタイム C++ テンプレート ライブラリ)
Event クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
explicit Event(  
   HANDLE h = HandleT::Traits::GetInvalidValue()  
);  
WRL_NOTHROW Event(  
   _Inout_ Event&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 イベントに対するハンドル。 既定では、`h` は `nullptr` に初期化されます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [Event クラス (Windows ランタイム C++ テンプレート ライブラリ)](../windows/event-class-windows-runtime-cpp-template-library.md)