---
title: "ComPtr::CopyTo メソッド | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::CopyTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CopyTo メソッド"
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::CopyTo メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定したポインターにこの ComPtr オブジェクトに関連付けられている現在のディレクトリまたは指定されたインターフェイスをコピーします。  
  
## 構文  
  
```  
HRESULT CopyTo(  
   _Deref_out_ InterfaceType** ptr  
);  
  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ void** ptr  
) const;  
template<  
   typename U  
>  
  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
) const;  
```  
  
#### パラメーター  
 `U`  
 型の名前。  
  
 `ptr`  
 この操作が完了すると、要求されたインターフェイスへのポインター。  
  
 `riid`  
 インターフェイス ID  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、QueryInterface の操作が失敗した理由を示す HRESULT。  
  
## 解説  
 インターフェイスへのポインターのコピーがこの ComPtr オブジェクトに関連付けられた最初の関数の戻り値。  この関数は、常に S\_OK を返します。  
  
 2 番目の関数は `riid` パラメーターで指定されたインターフェイスのこの ComPtr オブジェクトに関連付けられたインターフェイスの QueryInterface を処理します。  
  
 3 番目の関数は `U` パラメーターの基のインターフェイスに対してこの ComPtr オブジェクトに関連付けられたインターフェイスの QueryInterface を処理します。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ComPtr クラス](../windows/comptr-class.md)