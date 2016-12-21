---
title: "RuntimeClass クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClass クラス"
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClass クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した数のインターフェイスを継承し、指定した [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]、クラシック COM、および弱い参照のサポートが用意されているインスタンス化されたクラスを表します。  
  
 通常、WRL 型は `RuntimeClass` から派生します。これは、このクラスで `AddRef`、`Release`、および `QueryInterface` が実装され、モジュールの全体的な参照カウントを管理できるためです。  
  
## 構文  
  
```  
template <  
   typename I0,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
class RuntimeClass : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT, RuntimeClassFlags<WinRt>>;  
  
template <  
   unsigned int classFlags,  
   typename I0,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8  
>  
class RuntimeClass<RuntimeClassFlags<classFlags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT, RuntimeClassFlags<classFlags> >;  
```  
  
#### パラメーター  
 `I0`  
 0 番目のインターフェイス ID です \(必須\)。  
  
 `I1`  
 1 番目のインターフェイス ID です \(オプション\)。  
  
 `I2`  
 2 番目のインターフェイス ID です \(オプション\)。  
  
 `I3`  
 3 番目のインターフェイス ID です \(オプション\)。  
  
 `I4`  
 4 番目のインターフェイス ID です \(オプション\)。  
  
 `I5`  
 5 番目のインターフェイス ID です \(オプション\)。  
  
 `I6`  
 6 番目のインターフェイス ID です \(オプション\)。  
  
 `I7`  
 7 番目のインターフェイス ID です \(オプション\)。  
  
 `I8`  
 8 番目のインターフェイス ID です \(オプション\)。  
  
 `I9`  
 9 番目のインターフェイス ID です \(オプション\)。  
  
 `classFlags`  
 1 つ以上の [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 列挙値の組み合わせです。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[RuntimeClass::RuntimeClass コンストラクター](../windows/runtimeclass-runtimeclass-constructor.md)|RuntimeClass クラスの現在のインスタンスを初期化します。|  
|[RuntimeClass::~RuntimeClass デストラクター](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|RuntimeClass クラスの現在のインスタンスの初期化を解除します。|  
  
## 継承階層  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `RuntimeClass`  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)