---
title: "SimpleActivationFactory::GetRuntimeClassName メソッド | Microsoft Docs"
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
  - "module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName"
dev_langs: 
  - "C++"
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SimpleActivationFactory::GetRuntimeClassName メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`Base` クラス テンプレート パラメーターで指定されたクラスのインスタンスのランタイム クラスの名前を取得します。  
  
## 構文  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
#### パラメーター  
 `runtimeName`  
 この操作が完了すると、ランタイム クラスの名前。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、エラーを示す HRESULT を返します。  
  
## 解説  
 \_\_WRL\_STRICT が定義されている場合、アサートのエラーが `Base` クラス テンプレート パラメーターで指定されたクラスが [RuntimeClass](../windows/runtimeclass-class.md)から派生されなければ呼び出したり、または WinRt または WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) の列挙値が設定されません。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)