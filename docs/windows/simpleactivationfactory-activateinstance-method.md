---
title: "SimpleActivationFactory::ActivateInstance メソッド | Microsoft Docs"
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
  - "module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivateInstance メソッド"
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SimpleActivationFactory::ActivateInstance メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定されたインターフェイスのインスタンスを作成します。  
  
## 構文  
  
```  
STDMETHOD(  
   ActivateInstance  
)(_Deref_out_ IInspectable **ppvObject);  
```  
  
#### パラメーター  
 `ppvObject`  
 この操作が完了したら、オブジェクト インスタンスへのポインターを `Base` クラス テンプレート パラメーターで指定します。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、エラーを示す HRESULT を返します。  
  
## 解説  
 \_\_WRL\_STRICT が定義されている場合、アサートのエラーはクラス テンプレート パラメーターで指定された基本クラスが [RuntimeClass](../windows/runtimeclass-class.md)から派生されなければ呼び出したり、または WinRt または WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) の列挙値が設定されません。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)