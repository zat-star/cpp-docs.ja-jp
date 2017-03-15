---
title: "SimpleClassFactory クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SimpleClassFactory クラス"
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# SimpleClassFactory クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

基本的な機能を基本クラスを作成する手順について説明します。  
  
## 構文  
  
```  
template<  
   typename Base  
>  
class SimpleClassFactory : public ClassFactory<>;  
```  
  
#### パラメーター  
 `Base`  
 基本クラスです。  
  
## 解説  
 基本クラスが既定のコンストラクターを提供する必要があります。  
  
 次のコード例は [ActivatableClassWithFactoryEx](../Topic/ActivatableClass%20Macros.md) マクロの SimpleClassFactory を使用する方法を示します。  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[SimpleClassFactory::CreateInstance メソッド](../windows/simpleclassfactory-createinstance-method.md)|指定されたインターフェイスのインスタンスを作成します。|  
  
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
  
 `ClassFactory`  
  
 `SimpleClassFactory`  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)