---
title: "ActivationFactory::GetTrustLevel メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::GetTrustLevel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetTrustLevel メソッド"
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivationFactory::GetTrustLevel メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在の ActivationFactory がインスタンス化するオブジェクトの信頼レベルを取得します。  
  
## 構文  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### パラメーター  
 `trustLvl`  
 この操作が完了すると、ActivationFactory がインスタンス化するランタイム クラスの信頼レベル。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合、アサーション エラーが表示され、`trustLvl` は FullTrust に設定されます。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ActivationFactory クラス](../windows/activationfactory-class.md)