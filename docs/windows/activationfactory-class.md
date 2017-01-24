---
title: "ActivationFactory クラス | Microsoft Docs"
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
  - "module/Microsoft::WRL::ActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivationFactory クラス"
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActivationFactory クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

一つ以上のクラスが Windows ランタイムでアクティブ化することができます。  
  
## 構文  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;  
```  
  
#### パラメーター  
 `I0`  
 zeroth インターフェイス。  
  
 `I1`  
 最初のインターフェイス。  
  
 `I2`  
 2 番目のインターフェイス。  
  
## 解説  
 ActivationFactory は IActivationFactory インターフェイスに登録メソッドと基本機能を提供します。  また ActivationFactory を使用するカスタム ファクトリの実装を提供します。  
  
 次のコードは、シンボルで ActivationFactory を使用する方法について説明します。  
  
 [!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]  
  
 次のコードは、3 以上のインターフェイス ID を指定するために [実装](../Topic/Implements%20Structure.md) 構造体を使用する方法を示します。  
  
 `struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[ActivationFactory::ActivationFactory コンストラクター](../windows/activationfactory-activationfactory-constructor.md)|ActivationFactory クラスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[ActivationFactory::AddRef メソッド](../windows/activationfactory-addref-method.md)|ActivationFactory の現在のオブジェクトの参照カウントをインクリメントします。|  
|[ActivationFactory::GetIids メソッド](../windows/activationfactory-getiids-method.md)|実装されたインターフェイスの ID の配列を取得します。|  
|[ActivationFactory::GetRuntimeClassName メソッド](../windows/activationfactory-getruntimeclassname-method.md)|現在の ActivationFactory がインスタンス化するオブジェクトのランタイム クラスの名前を取得します。|  
|[ActivationFactory::GetTrustLevel メソッド](../windows/activationfactory-gettrustlevel-method.md)|現在の ActivationFactory がインスタンス化するオブジェクトの信頼レベルを取得します。|  
|[ActivationFactory::QueryInterface メソッド](../windows/activationfactory-queryinterface-method.md)|指定されたインターフェイスへのポインターを取得します。|  
|[ActivationFactory::Release メソッド](../windows/activationfactory-release-method.md)|ActivationFactory の現在のオブジェクトの参照カウントをデクリメントします。|  
  
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
  
 `ActivationFactory`  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)