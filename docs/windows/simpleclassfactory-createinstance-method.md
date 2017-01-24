---
title: "SimpleClassFactory::CreateInstance メソッド | Microsoft Docs"
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
  - "module/Microsoft::WRL::SimpleClassFactory::CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInstance メソッド"
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SimpleClassFactory::CreateInstance メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定されたインターフェイスのインスタンスを作成します。  
  
## 構文  
  
```  
  
STDMETHOD(  
   CreateInstance  
)  
   (_Inout_opt_ IUnknown* pUnkOuter,   
   REFIID riid,   
   _Deref_out_ void** ppvObject);  
```  
  
#### パラメーター  
 `pUnkOuter`  
 `nullptr`;でなければなりません。それ以外の場合、戻り値は CLASS\_E\_NOAGGREGATION です。  
  
 SimpleClassFactory は集約をサポートしません。  集計がサポートされ、作成されたオブジェクトが集計の一部は、`pUnkOuter` 集計の制御の IUnknown インターフェイスへのポインターです。  
  
 `riid`  
 作成するオブジェクトのインターフェイス ID。  
  
 `ppvObject`  
 この操作が完了したら、オブジェクト インスタンスへのポインターを `riid` パラメーターで指定します。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、エラーを示す HRESULT を返します。  
  
## 解説  
 \_\_WRL\_STRICT が定義されている場合、アサートのエラーはクラス テンプレート パラメーターで指定された基本クラスが [RuntimeClass](../windows/runtimeclass-class.md)から派生されなければ呼び出したり、または ClassicCom または WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) の列挙値が設定されません。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [SimpleClassFactory クラス](../windows/simpleclassfactory-class.md)