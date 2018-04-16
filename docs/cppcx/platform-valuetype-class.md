---
title: "Platform::valuetype クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
dev_langs:
- C++
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4b6fd3ada45e810b95a88090bc98c9305013aaa
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="platformvaluetype-class"></a>Platform::ValueType クラス
値の型のインスタンスの基底クラス。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public ref class ValueType : Object  
```  
  
## <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|[ValueType::ToString](#tostring)|オブジェクトの文字列形式を返します。 継承された[platform::object](../cppcx/platform-object-class.md)です。|  
  
### <a name="remarks"></a>コメント  
 ValueType クラスは、値型を構築するために使用されます。 ValueType は Object (基本メンバーを持つ) から派生します。 ただし、コンパイラは、それらのメンバーを、ValueType クラスから派生する値型からデタッチします。 値型がボックス化されると、コンパイラは、その基本メンバーを再びアタッチします。  
  
### <a name="requirements"></a>必要条件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  

## <a name="tostring"></a> ValueType::ToString メソッド
オブジェクトの文字列形式を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
Platform::String ToString();  
```  
  
### <a name="return-value"></a>戻り値  
 値を表す platform::string を指定します。  
    
## <a name="see-also"></a>参照  
 [Platform 名前空間](../cppcx/platform-namespace-c-cx.md)