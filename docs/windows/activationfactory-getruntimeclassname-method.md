---
title: "ActivationFactory::GetRuntimeClassName メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRuntimeClassName メソッド"
ms.assetid: 74e34f0a-9c51-4b40-89f5-45c6c5886ece
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivationFactory::GetRuntimeClassName メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在の ActivationFactory がインスタンス化するオブジェクトのランタイム クラスの名前を取得します。  
  
## 構文  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
#### パラメーター  
 `runtimeName`  
 この操作が完了すると、現在の ActivationFactory がインスタンス化するオブジェクトのランタイム クラスの名前を含む文字列へのハンドル。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は失敗を示す HRESULT を返します。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ActivationFactory クラス](../windows/activationfactory-class.md)