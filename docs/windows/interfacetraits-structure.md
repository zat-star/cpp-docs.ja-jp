---
title: "InterfaceTraits 構造体 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::InterfaceTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InterfaceTraits 構造体"
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InterfaceTraits 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
  
template<  
   typename CloakedType  
>  
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;  
  
template<>  
struct __declspec(novtable) InterfaceTraits<Nil>;  
```  
  
#### パラメーター  
 `I0`  
 インターフェイスの名前。  
  
 `CloakedType`  
 RuntimeClass、実装と ChainInterfaces のサポートされるインターフェイス ID の一覧にないインターフェイスです。  
  
## 解説  
 インターフェイスのような共通の特性を実装します。  
  
 2 番目のテンプレートはマスク インターフェイス用に特化したクラスです。  3 番目のテンプレートは、パラメーター用に特化したクラスです。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`Base`|`I0` テンプレート パラメーターのシノニムです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[InterfaceTraits::CanCastTo メソッド](../Topic/InterfaceTraits::CanCastTo%20Method.md)|指定したポインターが `Base`へのポインターにキャストすることができるかどうかを示します。|  
|[InterfaceTraits::CastToBase メソッド](../windows/interfacetraits-casttobase-method.md)|`Base`へのポインターに指定したポインターをキャストします。|  
|[InterfaceTraits::CastToUnknown メソッド](../windows/interfacetraits-casttounknown-method.md)|IUnknown へのポインターに指定したポインターをキャストします。|  
|[InterfaceTraits::FillArrayWithIid メソッド](../windows/interfacetraits-fillarraywithiid-method.md)|インデックスの引数で指定された配列の要素に `Base` のインターフェイス ID を割り当てます。|  
|[InterfaceTraits::Verify メソッド](../Topic/InterfaceTraits::Verify%20Method.md)|ベースが派生されることを確認します。|  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[InterfaceTraits::IidCount 定数](../Topic/InterfaceTraits::IidCount%20Constant.md)|InterfaceTraits の現在のオブジェクトに関連付けられたインターフェイス ID の数値を保持します。|  
  
## 継承階層  
 `InterfaceTraits`  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)