---
title: "FtmBase::DisconnectObject メソッド | Microsoft Docs"
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
  - "ftm/Microsoft::WRL::FtmBase::DisconnectObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DisconnectObject メソッド"
ms.assetid: 33253eec-3a65-4e72-8525-0249245a4790
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# FtmBase::DisconnectObject メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

強制的にオブジェクトに対する外部接続を解放します。  オブジェクトのサーバーがシャットダウンする前にこのオブジェクトのメソッドの実装を呼び出します。  
  
## 構文  
  
```  
STDMETHODIMP DisconnectObject(  
   __in DWORD dwReserved  
) override;  
```  
  
#### パラメーター  
 `dwReserved`  
 今後使用するために予約されています。0 にする必要があります。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、エラーを示す HRESULT を返します。  
  
## 必要条件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [FtmBase クラス](../windows/ftmbase-class.md)