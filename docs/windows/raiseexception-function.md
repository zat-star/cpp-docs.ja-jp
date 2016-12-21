---
title: "RaiseException 関数 | Microsoft Docs"
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
  - "internal/Microsoft::WRL::Details::RaiseException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RaiseException 関数"
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RaiseException 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
inline void __declspec(noreturn)  
   RaiseException(  
      HRESULT hr,   
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);  
```  
  
#### パラメーター  
 `hr`  
 発生させる例外の例外コード; つまり、操作が失敗した場合に HRESULT。  
  
 `dwExceptionFlags`  
 継続的な例外を示すフラグ \(フラグ値はゼロ\) や noncontinuable 例外 \(フラグ値は 0 以外のです\)。  既定では、例外 noncontinuable です。  
  
## 解説  
 呼び出し元のスレッドで例外を発生させます。  
  
 詳細については、Windows の **RaiseException** 関数を参照します。  
  
## 必要条件  
 **ヘッダー:** internal.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)