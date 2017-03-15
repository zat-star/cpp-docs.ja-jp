---
title: "SimpleActivationFactory クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SimpleActivationFactory クラス"
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# SimpleActivationFactory クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

基本的な機能を Windows ランタイムまたは標準的な COM の基本クラスを作成する手順について説明します。  
  
## 構文  
  
```  
template<  
   typename Base  
>  
class SimpleActivationFactory : public ActivationFactory<>;  
```  
  
#### パラメーター  
 `Base`  
 基本クラスです。  
  
## 解説  
 基本クラスが既定のコンストラクターを提供する必要があります。  
  
 次のコード例は [ActivatableClassWithFactoryEx](../Topic/ActivatableClass%20Macros.md) マクロの SimpleActivationFactory を使用する方法を示します。  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[SimpleActivationFactory::ActivateInstance メソッド](../windows/simpleactivationfactory-activateinstance-method.md)|指定されたインターフェイスのインスタンスを作成します。|  
|[SimpleActivationFactory::GetRuntimeClassName メソッド](../windows/simpleactivationfactory-getruntimeclassname-method.md)|`Base` クラス テンプレート パラメーターで指定されたクラスのインスタンスのランタイム クラスの名前を取得します。|  
|[SimpleActivationFactory::GetTrustLevel メソッド](../Topic/SimpleActivationFactory::GetTrustLevel%20Method.md)|`Base` クラス テンプレート パラメーターで指定されたクラスのインスタンスの信頼レベルを取得します。|  
  
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
  
 `SimpleActivationFactory`  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)