---
title: "RuntimeClass::GetRuntimeClassName メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRuntimeClassName メソッド"
ms.assetid: f6388163-fe65-4948-a4bc-ae6826f480e7
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClass::GetRuntimeClassName メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

RuntimeClass の現在のオブジェクトのランタイム クラスの名前を取得します。  
  
## 構文  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
## パラメーター  
 `runtimeName`  
 この操作が完了すると、ランタイム クラスの名前。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、エラーを示す HRESULT を返します。  
  
## 解説  
 Assert のエラーが\_\_WRL\_STRICT\_\_or の\_\_WRL\_FORCE\_INSPECTABLE\_CLASS\_MACRO が定義されて表示されます。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)