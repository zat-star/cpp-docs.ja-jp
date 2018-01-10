---
title: "Event::operator = 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Event::operator=
dev_langs: C++
helpviewer_keywords: operator= operator
ms.assetid: d8fe9820-8856-4899-9553-56226bdc4945
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: de46ba0d6749120fc391b4a55527904ed1321ad9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="eventoperator-operator"></a>Event::operator= 演算子
指定された Event 参照を現在の Event インスタンスに割り当てます。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW Event& operator=(  
   _Inout_ Event&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 イベント インスタンスに右辺値の参照。  
  
## <a name="return-value"></a>戻り値  
 現在の Event インスタンスへのポインター。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [Event クラス (Windows ランタイム C++ テンプレート ライブラリ)](../windows/event-class-windows-runtime-cpp-template-library.md)