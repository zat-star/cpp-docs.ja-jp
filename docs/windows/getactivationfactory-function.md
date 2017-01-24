---
title: "GetActivationFactory 関数 | Microsoft Docs"
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
  - "module/Microsoft::WRL::Details::GetActivationFactory"
  - "client/ABI::Windows::Foundation::GetActivationFactory"
  - "client/Windows::Foundation::GetActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetActivationFactory 関数"
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetActivationFactory 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート パラメーターで指定された型のアクティベーション ファクトリを取得します。  
  
## 構文  
  
```  
template<  
   typename T  
>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
#### パラメーター  
 `T`  
 アクティベーション ファクトリの型を指定するテンプレート パラメーター。  
  
 `activatableClassId`  
 生成アクティベーション ファクトリができるクラスの名前。  
  
 `factory`  
 この操作が完了すると、型 `T`のアクティベーション ファクトリへの参照。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、この操作が失敗した理由を示すエラー HRESULT。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Windows::Foundation  
  
## 参照  
 [Windows::Foundation 名前空間](../Topic/Windows::Foundation%20Namespace.md)