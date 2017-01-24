---
title: "ChainInterfaces 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ChainInterfaces 構造体"
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ChainInterfaces 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

一連のインターフェイス ID に適用できる初期化関数と検証を指定します。  
  
## 構文  
  
```  
template <  
   typename I0,  
   typename I1,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct ChainInterfaces : I0;  
template <  
   typename DerivedType,  
   typename BaseType,  
   bool hasImplements,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8,  
   typename I9  
>  
struct ChainInterfaces<MixIn<DerivedType, BaseType, hasImplements>, I1, I2, I3, I4, I5, I6, I7, I8, I9>;  
```  
  
#### パラメーター  
 `I0`  
 \(必須\) インターフェイス ID 0。  
  
 `I1`  
 \(必須\) インターフェイス ID 1。  
  
 `I2`  
 \(省略可能\) インターフェイス ID 2。  
  
 `I3`  
 \(省略可能\) インターフェイス ID 3。  
  
 `I4`  
 \(省略可能\) インターフェイス ID 4。  
  
 `I5`  
 \(省略可能\) インターフェイス ID 5。  
  
 `I6`  
 \(省略可能\) インターフェイス ID 6。  
  
 `I7`  
 \(省略可能\) インターフェイス ID 7。  
  
 `I8`  
 \(省略可能\) インターフェイス ID 8。  
  
 `I9`  
 \(省略可能\) インターフェイス ID 9。  
  
 `DerivedType`  
 派生型。  
  
 `BaseType`  
 派生型の基本型。  
  
 `hasImplements`  
 `true`の手段が [実装](../Topic/Implements%20Structure.md) 構造体から派生しないクラスとともに [MixIn](../windows/mixin-structure.md) 構造体を使用できるブール値。  
  
## メンバー  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[ChainInterfaces::CanCastTo メソッド](../Topic/ChainInterfaces::CanCastTo%20Method.md)|指定されたインターフェイス ID が ChainInterface のテンプレート パラメーターで定義されているクラスのそれぞれにキャストすることができるかどうかを示します。|  
|[ChainInterfaces::CastToUnknown メソッド](../windows/chaininterfaces-casttounknown-method.md)|IUnknown へのポインターに `I0` テンプレート パラメーターによって定義される型のインターフェイス ポインターをキャストします。|  
|[ChainInterfaces::FillArrayWithIid メソッド](../Topic/ChainInterfaces::FillArrayWithIid%20Method.md)|指定した位置に `I0` テンプレート パラメーターで定義されているインターフェイス ID を指定された配列のインターフェイス ID が格納されます。|  
|[ChainInterfaces::Verify メソッド](../windows/chaininterfaces-verify-method.md)|`I9` してテンプレート パラメーター `I0` で定義されている各インターフェイスが IUnknown または IInspectable から継承すること、および `I0` が `I1` から `I9`から継承することを確認します。|  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[ChainInterfaces::IidCount 定数](../windows/chaininterfaces-iidcount-constant.md)|`I9`してテンプレート `I0` パラメーターで指定されたインターフェイスに含まれるインターフェイス ID の総数。|  
  
## 継承階層  
 `I0`  
  
 `ChainInterfaces`  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)