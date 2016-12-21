---
title: "ActivationFactoryCallback 関数 | Microsoft Docs"
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
  - "module/Microsoft::WRL::Details::ActivationFactoryCallback"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivationFactoryCallback 関数"
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActivationFactoryCallback 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(  
   HSTRING activationId,  
   IActivationFactory **ppFactory  
);  
```  
  
#### パラメーター  
 `activationId`  
 ランタイム クラスの名前を指定する文字列へのハンドル。  
  
 `ppFactory`  
 この操作が完了すると、`activationId`パラメーターに対応するアクティベーション ファクトリ。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は失敗を示す HRESULT を返します。  高いエラー HRESULT は CLASS\_E\_CLASSNOTAVAILABLE と E\_INVALIDARG です。  
  
## 解説  
 指定アクティベーション ID のアクティベーション ファクトリを取得します。  
  
 Windows ランタイムは、ランタイム クラスの名前で指定されたオブジェクトを要求するには、このコールバック関数が呼び出されます。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)