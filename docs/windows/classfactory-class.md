---
title: "ClassFactory クラス | Microsoft Docs"
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
  - "module/Microsoft::WRL::ClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ClassFactory クラス"
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ClassFactory クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

IClassFactory インターフェイスの基本機能を実装します。  
  
## 構文  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ClassFactory : public Details::RuntimeClass<  
   typename Details::InterfaceListHelper<IClassFactory,   
   I0,   
   I1,   
   I2,   
   Details::Nil>::TypeT,   
   RuntimeClassFlags<ClassicCom | InhibitWeakReference>,   
      false>;  
```  
  
#### パラメーター  
 `I0`  
 zeroth インターフェイス。  
  
 `I1`  
 最初のインターフェイス。  
  
 `I2`  
 2 番目のインターフェイス。  
  
## 解説  
 ユーザーが定義するファクトリの実装を提供するために `ClassFactory` を使用します。  
  
 次のプログラミング パターンがクラス ファクトリで 3 つ以上のインターフェイスを指定するために [実装](../Topic/Implements%20Structure.md) 構造体を使用する方法を示します。  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[ClassFactory::ClassFactory コンストラクター](../Topic/ClassFactory::ClassFactory%20Constructor.md)||  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[ClassFactory::AddRef メソッド](../Topic/ClassFactory::AddRef%20Method.md)|ClassFactory の現在のオブジェクトの参照カウントをインクリメントします。|  
|[ClassFactory::LockServer メソッド](../windows/classfactory-lockserver-method.md)|ClassFactory の現在のオブジェクトによって追跡された基になるオブジェクトの数をインクリメントするか、デクリメントします。|  
|[ClassFactory::QueryInterface メソッド](../windows/classfactory-queryinterface-method.md)|パラメーターで指定したインターフェイスへのポインターを取得します。|  
|[ClassFactory::Release メソッド](../windows/classfactory-release-method.md)|ClassFactory の現在のオブジェクトの参照カウントをデクリメントします。|  
  
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
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)   
 [RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md)