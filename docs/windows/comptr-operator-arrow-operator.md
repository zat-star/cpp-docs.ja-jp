---
title: "ComPtr::operator-&gt; 演算子 | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator-> 演算子"
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator-&gt; 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在のテンプレート パラメーターによって指定された型へのポインターを取得します。  
  
## 構文  
  
```  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## 戻り値  
 現在のテンプレート型の名前で指定される型へのポインター。  
  
## 解説  
 このヘルパー関数は、STDMETHOD マクロの使用による不要なオーバーヘッドを削除します。  この関数は、IUnknown の型を仮想の代わりにプライベートになります。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ComPtr クラス](../windows/comptr-class.md)