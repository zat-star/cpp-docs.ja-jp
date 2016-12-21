---
title: "ArgTraits 構造体 | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::ArgTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ArgTraits 構造体"
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ArgTraits 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template<  
   typename TMemberFunction  
>  
struct ArgTraits;  
template<  
   typename TDelegateInterface  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;  
```  
  
#### パラメーター  
 `TMemberFunction`  
 一致しない ArgTraits 構造体の TypeName パラメーターは、メソッド シグネチャを呼び出します。  
  
 `TDelegateInterface`  
 デリゲート インターフェイス。  
  
 `TArg1`  
 呼び出すメソッドの最初の引数の型です。  
  
 `TArg2`  
 メソッド呼び出しの 2 番目の引数の型。  
  
 `TArg3`  
 メソッド呼び出しの 3 番目の引数の型。  
  
 `TArg4`  
 メソッド呼び出しの 4 番目の引数の型。  
  
 `TArg5`  
 メソッド呼び出しの 5 番目の引数の型。  
  
 `TArg6`  
 メソッド呼び出しの 6 番目の引数の型。  
  
 `TArg7`  
 メソッド呼び出しの 7 番目の引数の型。  
  
 `TArg8`  
 メソッド呼び出しの 8 番目の引数の型。  
  
 `TArg9`  
 メソッド呼び出しの 9 番目の引数の型。  
  
## 解説  
 `ArgTraits` 構造体は指定されたデリゲート インターフェイスとパラメーターの指定数が同じ名前のメンバー関数を宣言します。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`Arg1Type`|TArg1 の typedef。|  
|`Arg2Type`|TArg2 の typedef。|  
|`Arg3Type`|TArg3 の typedef。|  
|`Arg4Type`|TArg4 の typedef。|  
|`Arg5Type`|TArg5 の typedef。|  
|`Arg6Type`|TArg6 の typedef。|  
|`Arg7Type`|TArg7 の typedef。|  
|`Arg8Type`|TArg8 の typedef。|  
|`Arg9Type`|TArg9 の typedef。|  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[ArgTraits::args 定数](../windows/argtraits-args-constant.md)|デリゲートの呼び出しインターフェイス メソッドのパラメーターの数を記録します。|  
  
## 継承階層  
 `ArgTraits`  
  
## 必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)