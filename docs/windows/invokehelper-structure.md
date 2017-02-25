---
title: "InvokeHelper 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::InvokeHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InvokeHelper 構造体"
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InvokeHelper 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template<  
   typename TDelegateInterface,  
   typename TCallback,  
   unsigned int argCount  
>  
struct InvokeHelper;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 0> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 1> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 2> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 3> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 4> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 5> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 6> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 7> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 8> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 9> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
```  
  
#### パラメーター  
 `TDelegateInterface`  
 `TCallback`  
 イベント ハンドラー関数の型。  
  
 `argCount`  
 InvokeHelper の特化型引数の数。  
  
## 解説  
 引数の指定数と型に基づいて Invoke\(\) のメソッドの実装を提供します。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`Traits`|各イベント ハンドラーの引数の型を定義するクラスのシノニムです。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[InvokeHelper::InvokeHelper コンストラクター](../windows/invokehelper-invokehelper-constructor.md)|InvokeHelper クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[InvokeHelper::Invoke メソッド](../windows/invokehelper-invoke-method.md)|シグネチャが引数に指定された回数を含むイベント ハンドラーが呼び出されます。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[InvokeHelper::callback\_ データ メンバー](../windows/invokehelper-callback-data-member.md)|イベントが発生すると、イベント ハンドラーの呼び出しを表します。|  
  
## 継承階層  
 `InvokeHelper`  
  
## 必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)