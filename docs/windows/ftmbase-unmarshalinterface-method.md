---
title: "FtmBase::UnmarshalInterface メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::UnmarshalInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnmarshalInterface メソッド"
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase::UnmarshalInterface メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

新しく作成されたプロキシを初期化し、そのプロキシへのインターフェイス ポインターを返します。  
  
## 構文  
  
```  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
#### パラメーター  
 `pStm`  
 インターフェイス ポインターがマーシャリングを解除されるストリームへのポインター。  
  
 `riid`  
 マーシャリングを解除される必要インターフェイスの識別子への参照。  
  
 `ppv`  
 この操作が完了したら、インターフェイス ポインターを取得ポインター変数のアドレスは `riid`にあります。  この操作が正常に終了した場合、\*`ppv` はマーシャリングを解除される必要インターフェイスを要求されたインターフェイス ポインターが含まれています。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合、E\_NOINTERFACE または E\_FAIL。  
  
## 必要条件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [FtmBase クラス](../windows/ftmbase-class.md)