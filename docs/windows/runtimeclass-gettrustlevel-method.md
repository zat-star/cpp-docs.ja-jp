---
title: "RuntimeClass::GetTrustLevel メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::GetTrustLevel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetTrustLevel メソッド"
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClass::GetTrustLevel メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

RuntimeClass オブジェクトの現在の信頼レベルを取得します。  
  
## 構文  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
## パラメーター  
 `trustLvl`  
 この操作が完了すると、RuntimeClass オブジェクトの現在の信頼レベル。  
  
## 戻り値  
 常には S\_OK を返します。  
  
## 解説  
 Assert のエラーが\_\_WRL\_STRICT\_\_or の\_\_WRL\_FORCE\_INSPECTABLE\_CLASS\_MACRO が定義されて表示されます。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)