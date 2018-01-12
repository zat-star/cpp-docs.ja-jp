---
title: "Platform::valuetype クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::ValueType::ToString
dev_langs: C++
helpviewer_keywords: Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4dba418e74affb2531e3ebbd43d95c35601e9a26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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

## <a name="tostring"></a>ValueType::ToString メソッド
オブジェクトの文字列形式を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
Platform::String ToString();  
```  
  
### <a name="return-value"></a>戻り値  
 値を表す platform::string を指定します。  
    
## <a name="see-also"></a>参照  
 [Platform 名前空間](../cppcx/platform-namespace-c-cx.md)