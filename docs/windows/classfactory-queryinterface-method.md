---
title: "ClassFactory::QueryInterface メソッド | Microsoft Docs"
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
  - "module/Microsoft::WRL::ClassFactory::QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface メソッド"
ms.assetid: 9593881f-4585-4d70-8ca6-b328918d4d6b
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ClassFactory::QueryInterface メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

パラメーターで指定したインターフェイスへのポインターを取得します。  
  
## 構文  
  
```  
STDMETHOD(  
   QueryInterface  
)(REFIID riid, _Deref_out_ void **ppvObject);  
```  
  
#### パラメーター  
 `riid`  
 インターフェイス ID  
  
 `ppvObject`  
 この操作が完了したら、インターフェイスへのポインターが `riid`パラメーターで指定します。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は失敗を示す HRESULT を返します。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ClassFactory クラス](../windows/classfactory-class.md)